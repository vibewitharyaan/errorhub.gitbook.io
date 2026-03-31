# ZSX Multicharacter

If you're using `ZSX_Multicharacter`, you may need to make some additional modifications. Follow the instructions below based on your clothing script. _<mark style="color:orange;">**If you're not using**</mark><mark style="color:orange;">**&#x20;**</mark><mark style="color:orange;">**`ZSX_Multicharacter`**</mark><mark style="color:orange;">**, you can skip this section**</mark>._

{% tabs %}
{% tab title="qb-clothing" %}
{% hint style="info" %}
If you're using `qb-clothing`, no additional modifications are needed as long as you've already configured it and followed [this step](/broken/pages/92o5uKFK46ECbS7ftXqN#qb-clothing).
{% endhint %}
{% endtab %}

{% tab title="illenium-appearance" %}
1. Navigate to <mark style="color:yellow;">`framework_functions.lua`</mark> in the <mark style="color:yellow;">`ZSX_Multicharacter/client/framework`</mark> folder.
2. Locate the following line in the file:

```lua
exports['illenium-appearance']:startPlayerCustomization(function (skin)
```

3. Just below the line `HandleHud(false)` (around line 92), insert the following code:

```lua
TriggerEvent("eh_cutscene:client:StartCutscene") -->> Start eh_cutscene
print('^2Started eh_cutscene')
```

<figure><img src="../../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>This is how the modified client code should look like</p></figcaption></figure>
{% endtab %}

{% tab title="fivem-appearance" %}
1. Navigate to <mark style="color:yellow;">`framework_functions.lua`</mark> in the <mark style="color:yellow;">`ZSX_Multicharacter/client/framework`</mark> folder.
2. Locate the following line in the file:

```lua
exports.bl_appearance:InitialCreation(function()
```

3. Just below the line `HandleHud(false)` (around line 113), insert the following code:

```lua
TriggerEvent("eh_cutscene:client:StartCutscene") -->> Start eh_cutscene
print('^2Started eh_cutscene')
```

<figure><img src="../../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>This is how the modified client code should look like</p></figcaption></figure>
{% endtab %}

{% tab title="bl_appearance" %}
1. Navigate to <mark style="color:yellow;">`framework_functions.lua`</mark> in the <mark style="color:yellow;">`ZSX_Multicharacter/client/framework`</mark> folder.
2. Locate the following line in the file:

```lua
exports['fivem-appearance']:startPlayerCustomization(function (skin)
```

3. Just below the line `HandleHud(false)` (around line 79), insert the following code:

```lua
TriggerEvent("eh_cutscene:client:StartCutscene") -->> Start eh_cutscene
print('^2Started eh_cutscene')
```

<figure><img src="../../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>This is how the modified client code should look like</p></figcaption></figure>
{% endtab %}
{% endtabs %}

