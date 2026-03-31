# Vehicle Keys

If you're facing an issue where taxi doors unexpectedly close when players try to enter, it's likely due to the vehicle keys script on your server. This happens when the script forcefully locks NPC vehicles, unintentionally locking taxi doors as well.

We've already applied an inbuilt patch, but sometimes vehicle keys scripts override it. To fully resolve this, follow the steps below.

{% tabs %}
{% tab title="qb-vehiclekeys" %}
If you're using `qb-vehiclekeys` and NPC vehicles are set to lock, follow these steps:

1. Open the `main.lua` file in the `qb-vehiclekeys/client` folder.
2. Go to line 58, and modify the file as shown below:

```lua
else -- > approx line 57
    if not exports["eh_cutscene"]:isVehicleTaxi(entering) then
        TriggerServerEvent('qb-vehiclekeys:server:setVehLockState', NetworkGetNetworkIdFromEntity(entering), 1)
        TriggerServerEvent('qb-vehiclekeys:server:AcquireVehicleKeys', plate)

        --Make passengers flee
        local pedsInVehicle = GetPedsInVehicle(entering)
        for _, pedInVehicle in pairs(pedsInVehicle) do
            if pedInVehicle ~= GetPedInVehicleSeat(entering, -1) then
                MakePedFlee(pedInVehicle)
            end
        end
    end
end
```

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>This is how the modified code should look like</p></figcaption></figure>
{% endtab %}

{% tab title="qbx_vehiclekeys" %}
If you're using `qbx_vehiclekeys` and NPC vehicles are set to lock, follow these steps:

1. Open the `main.lua` file in the `qbx_vehiclekeys\client` folder.
2. Go to line 252, and modify the file as shown below:

```lua
local function onVehicleAttemptToEnter(vehicle)
    if Entity(vehicle).state.doorslockstate then return end

    if exports["eh_cutscene"]:isVehicleTaxi(vehicle) then return end

    local ped = GetPedInVehicleSeat(vehicle, -1)
    if IsPedAPlayer(ped) then return end

    local isLocked = not GetVehicleConfig(vehicle).noLock and getIsVehicleInitiallyLocked(vehicle, ped and ped ~= 0)
    local lockState = isLocked and 2 or 1
    SetVehicleDoorsLocked(vehicle, lockState)
    TriggerServerEvent('qb-vehiclekeys:server:setVehLockState', NetworkGetNetworkIdFromEntity(vehicle), lockState)
end
```

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption><p>This is how the modified code should look like</p></figcaption></figure>
{% endtab %}
{% endtabs %}

{% hint style="info" %}
If you're not using either of these two vehicle keys scripts and still facing the issue, you can easily resolve it using the same method. Alternatively, you can join our Discord for further support.
{% endhint %}
