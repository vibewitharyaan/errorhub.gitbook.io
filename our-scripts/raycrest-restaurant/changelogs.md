---
icon: clock-rotate-left
---

# changelogs

{% tabs %}
{% tab title="config.lua" %}
```lua
ehConfig = {}

ehConfig.debug = {
    code = false,         -- Want to see helpful debug messages in your console?
    zone = false,         -- Want to see where interaction zones are in-game?
    command = "cutscene" -- What command would you like to use to test the cutscene? (Only works if debug messages are enabled)
}

ehConfig.resources = {
    notify = 'ox',        -- Which notification system are you using? (Options: qb/okok/ox/esx/custom)
    textui = 'ox',        -- Which text UI system are you using? (Options: qb/ox/okok/esx/custom)
    fuel = 'LegacyFuel',     -- Which fuel system are you using? (Options: LegacyFuel/ps-fuel/cdn-fuel/ox_fuel/custom)
    vehiclekeys = 'qb',   -- Which vehicle keys system are you using? (Options: qb/okok/custom)
    menu = 'ox',          -- Which menu system are you using? (Options: qb/ox)
    mail = 'qb',          -- Which mail system are you using? (Options: qb/qs/gks/custom)
}

-- Framework Settings - Using QB/QBOX or ESX?
ehConfig.framework = {
    folder = {
        qb = "qb-core",     -- What's the name of your QB-Core folder? (If using qbox dont change this)
        esx = "es_extended" -- What's the name of your ESX folder?
    }
}

-- Cutscene Settings - Customize your player's arrival!
ehConfig.cutscene = {
    enable = true,     -- Would you like to show the intro cutscene when players first join?
    only = false,      -- Want to show just the cutscene without any taxi/rental services after?
    lamarPart = false, -- Would you like Lamar to appear in the cutscene?

    -- How should your plane passengers look?
    -- For each passenger, you can customize:
    -- - Their basic appearance (head, hair)
    -- - Their clothing (arms, pants, shoes, shirt, jacket)
    -- - The textures/colors of each item
    passengersAppearance = {
        [0] = {
            name = "MP_Plane_Passenger_1",
            model = "mp_m_freemode_01",
            outfit = {
                head = { variant = 21, texture = 0 },    -- Which face would you like? (variant = style, texture = skin tone)
                hair = { variant = 9, texture = 0 },     -- Which hairstyle? (variant = style, texture = color)
                arms = { variant = 1, texture = 0 },     -- Which sleeve style?
                pants = { variant = 9, texture = 0 },    -- Which pants style and color?
                shoes = { variant = 4, texture = 8 },    -- Which shoes and color?
                tshirt = { variant = 15, texture = 0 },  -- Which shirt style and design?
                jacket = { variant = 10, texture = 0 }   -- Which jacket style and color?
            }
        },
        [1] = {
            name = "MP_Plane_Passenger_2",
            model = "mp_f_freemode_01",
            outfit = {
                head = { variant = 13, texture = 0 },
                hair = { variant = 5, texture = 4 },
                arms = { variant = 1, texture = 0 },
                pants = { variant = 10, texture = 0 },
                shoes = { variant = 10, texture = 0 },
                tshirt = { variant = 11, texture = 2 },
                jacket = { variant = 10, texture = 0 }
            }
        },
        [2] = {
            name = "MP_Plane_Passenger_3",
            model = "mp_m_freemode_01",
            outfit = {
                head = { variant = 15, texture = 0 },
                hair = { variant = 1, texture = 4 },
                arms = { variant = 1, texture = 0 },
                pants = { variant = 0, texture = 1 },
                shoes = { variant = 1, texture = 7 },
                tshirt = { variant = 2, texture = 9 },
                jacket = { variant = 6, texture = 0 }
            }
        },
        [3] = {
            name = "MP_Plane_Passenger_4",
            model = "mp_f_freemode_01",
            outfit = {
                head = { variant = 14, texture = 0 },
                hair = { variant = 5, texture = 3 },
                arms = { variant = 3, texture = 0 },
                pants = { variant = 1, texture = 6 },
                shoes = { variant = 11, texture = 5 },
                tshirt = { variant = 2, texture = 0 },
                jacket = { variant = 3, texture = 12 }
            }
        },
        [4] = {
            name = "MP_Plane_Passenger_5",
            model = "mp_m_freemode_01",
            outfit = {
                head = { variant = 18, texture = 0 },
                hair = { variant = 15, texture = 3 },
                arms = { variant = 15, texture = 0 },
                pants = { variant = 2, texture = 5 },
                shoes = { variant = 4, texture = 6 },
                tshirt = { variant = 3, texture = 0 },
                jacket = { variant = 4, texture = 0 }
            }
        },
        [5] = {
            name = "MP_Plane_Passenger_6",
            model = "mp_f_freemode_01",
            outfit = {
                head = { variant = 27, texture = 0 },
                hair = { variant = 7, texture = 3 },
                arms = { variant = 11, texture = 0 },
                pants = { variant = 4, texture = 8 },
                shoes = { variant = 13, texture = 14 },
                tshirt = { variant = 5, texture = 3 },
                jacket = { variant = 2, texture = 7 }
            }
        },
        [6] = {
            name = "MP_Plane_Passenger_7",
            model = "mp_m_freemode_01",
            outfit = {
                head = { variant = 16, texture = 0 },
                hair = { variant = 15, texture = 1 },
                arms = { variant = 3, texture = 0 },
                pants = { variant = 5, texture = 6 },
                shoes = { variant = 2, texture = 8 },
                tshirt = { variant = 2, texture = 0 },
                jacket = { variant = 3, texture = 7 }
            }
        }
    }
}

-- After Cutscene - What happens next?
ehConfig.experience = {
    -- How would you like players to start their journey?
    -- 'blend': Players automatically get into a taxi (smoother, faster experience)
    -- 'choice': Players spawn at airport and choose between taxi or rental (more roleplay-focused)
    type = 'choice',

    -- If you chose 'blend' above:
    blend = {
        defaultTaxiModel = 2, -- Which taxi from your list below should be used? Index number from the list below.
    },

    -- If you chose 'choice' above:
    choice = {
        -- Will offer the rental and taxi services
        receptionist = {
            model = "a_m_y_stlat_01", -- How should your receptionist look? (Find models at: docs.fivem.net/docs/game-references/ped-models)
            coords = vec4(-1014.72, -2701.06, 13.78, 161.85), -- Where should your receptionist stand?
            scenario = "WORLD_HUMAN_CLIPBOARD", -- What should your receptionist be doing?
            marker = true -- Show a marker above receptionist? (Helps players locate them, but uses slightly more CPU temporarily but neglegible)
        },

        spawn = vec4(-1038.89, -2739.95, 13.85, 331.12), -- Where should players spawn after the cutscene?

        -- Want an airport icon on the map?
        blip = {
            enable = true, -- Should the airport be marked on the map?
            label = 'Los Santos Airport', -- What should we call it on the map?
            coords = vec3(-1037.88, -2738.34, 20.17), -- Where exactly should the icon be?
            sprite = 423, -- Which icon would you like? (Find icons at: docs.fivem.net/docs/game-references/blip-sprites)
            scale = 0.7, -- How big should the icon be? (0.1 - 1.0)
            color = 3 -- What color would you like? (Find colors at: docs.fivem.net/docs/game-references/blip-colors)
        }
    },

    paymentMethod = 'bank', -- Which payment method should be used for transactions? (bank/cash)
}

-- Welcome Message Configuration
ehConfig.welcomeMessage = {
    enable = true, -- Would you like to show a welcome message ui to the player after they spawn?
    cityName = "Los Santos", -- What should the city name be? (Minimum 10 and maximum 16 characters)
    color = "#00aeff", -- What should the color be?
    time = 4 -- How long should the message be shown? (in seconds)
}

-- Taxi Service Configuration
ehConfig.taxi = {
    enable = true,
    models = {
        -- What are the taxis available?
        -- label: What should this taxi be called in the menu?
        -- model: What is the spawn code for this taxi?
        -- price: How much should it cost to take this taxi? (Make price `0` if you want to take this taxi for free)
        -- image: What should be the preview image of the taxi? (put in web/assets/images/taxi) (Optional)
        -- customization: What should be the customization of the taxi? (Optional)
        -- colors: What should be the colors of the taxi? (Optional)
        -- extras: What should be the extras of the taxi? (Optional)
        -- livery: What should be the livery of the taxi? (Optional)
        -- plate: What should be the color of the plate of the taxi? (Optional)
        { label = "Motorcycle Taxi", model = "esskey", price = 50, image = "esskey.webp",
            customization = {
                colors = { primary = {246, 198, 0},
                secondary = {91, 137, 172} },
                livery = 7,
                plate = 1,
            }
        },
        { label = "Standard Taxi", model = "taxi",    price = 150, image = "taxi.webp",   customization = { plate = 1, } },
        { label = "Premium Taxi",  model = "jubilee", price = 300, image = "jubilee.webp", customization = { plate = 1, } },
        -- {
        --     label = "Custom Taxi",
        --     model = "example",
        --     price = 300,
        --     image = "example.png",
        --     customization = {
        --         colors = { primary = {255, 255, 255}, secondary = {255, 255, 255} },
        --         extras = { [1] = true, [2] = true, [3] = true },
        --         livery = 2
        --     }
        -- }
    },
    driver = {
        lamarAsDriver = true, -- Should Lamar be the driver of the taxi? (If lamarPart is false, this will be ignored)
        model = "s_m_o_busker_01",    -- What should the taxi driver look like? (If lamarAsDriver is true, this will be ignored)
        drivingStyles = { -- speed: The speed is in mph the max speed capping.
            normal = {style = 786621,     speed = 50.0, agression = 0.5}, -- 786619
            fast   = {style = 1074528317, speed = 80.0, agression = 1.0} -- 1074528317
        }
    },
    dropoff = {
        -- What drop-off locations are available?
        -- label: What should this location be called?
        -- fare:  How much should be the fare for this destination? (Make fare `0` if you want to goto that desitination for free)
        -- coords: Where is this location the taxi should drop off the player?
        -- skipCoords: Where should the taxi go when skipping? Use 'auto' for nearest road, or set custom coords with vector4(x,y,z,w)
        -- image: What should be the preview image of the destination (put in web/assets/images/locations)? (Optional)
        { label = "City Hall",                    fare = 0,  coords = vec3(-486.42, -253.12, 35.68),  skipCoords = "auto", image = "1.webp"},
        { label = "Integrity Tower Apartment",    fare = 10, coords = vec3(249.8, -644.05, 39.35),    skipCoords = vec4(289.13, -820.18, 29.22, 163.69), image = "2.webp"},
        { label = "So. Rockford Drive Apartment", fare = 10, coords = vec3(-686.79, -1095.06, 14.16), skipCoords = "auto", image = "3.webp"},
        { label = "Morningwood Blvd Apartment",   fare = 10, coords = vec3(-1287.53, -398.46, 35.56), skipCoords = "auto", image = "4.webp"},
        { label = "Tinsel Towers Apartment",      fare = 10, coords = vec3(-648.81, 28.47, 38.8),     skipCoords = "auto", image = "5.webp"},
        { label = "Fantastic Plaza Apartment",    fare = 10, coords = vec3(300.06, -1077.5, 28.91),   skipCoords = "auto", image = "6.webp"},
        { label = "Alta Street Apartment",        fare = 10, coords = vec3(-247.61, -1016.49, 28.68), skipCoords = "auto", image = "7.webp"},
    },
    spawn = { -- Where should the taxi's be spawned?
    	vec4(-1013.06, -2734.99, 13.27, 238.1),
    	vec4(-1023.82, -2728.57, 13.29, 238.77),
        vec4(-1040.57, -2719.0, 13.29, 239.87),
        vec4(-1051.72, -2712.87, 13.27, 240.68),
        vec4(-1019.99, -2490.69, 13.29, 148.39),
        vec4(-1026.62, -2501.35, 13.27, 148.47),
        vec4(-1070.71, -2578.55, 13.3, 147.78),
        vec4(-1076.69, -2589.3, 13.3, 149.02),
        vec4(-1023.78, -2489.97, 19.69, 149.69),
        vec4(-1030.16, -2500.6, 19.68, 148.44),
        vec4(-1036.01, -2510.94, 19.69, 147.28),
        vec4(-1044.22, -2524.92, 19.68, 144.49),
        vec4(-1050.47, -2536.17, 19.69, 146.99),
        vec4(-1056.24, -2546.15, 19.69, 144.95),
        vec4(-1064.46, -2560.15, 19.69, 145.99),
        vec4(-1070.89, -2571.44, 19.69, 148.51),
        vec4(-1076.86, -2581.83, 19.69, 150.07),
    }
}

-- Vehicle Rental Configuration
ehConfig.rental = {
    enable = true,                                  -- Do you want to enable the vehicle rental service?
    spawn = {                                       -- Where should rental vehicles spawn?
        vec4(-1012.47, -2695.86, 13.91, 59.81),
        vec4(-1009.74, -2691.14, 13.91, 60.41),
        vec4(-1017.89, -2689.72, 13.91, 240.15)
    },
    returnPoint = {
        model = 's_m_m_highsec_01',                     -- What should the return NPC look like?
        -- coords = vec4(114.97, -1079.43, 29.19, 358.95), -- Where should the return NPC be?
        coords = vec4(103.58, -1074.4, 29.19, 251.21), -- Where should the return NPC be?
        scenario = 'WORLD_HUMAN_CLIPBOARD',             -- What should the return NPC be doing?
        refund = {
            enable = true,  -- Should the money be refunded when the rental vehicle is returned?
            percentage = 50, -- How much percentage of the vehicle price should be refunded? (0-100)
            kick = true,    -- Should players attempting to exploit the refund system without renting a vehicle be kicked from the server?
        },
        blip = {
            label = 'Rental Return', -- What should the return point be called on the map?
            sprite = 225,            -- What should the map icon look like? (Car icon)
            scale = 0.7,             -- How big should the map icon be?
            color = 2,               -- What color should the map icon be? (Green)
        }
    },
    vehicles = {
        -- What are the vehicles available for rental?
        -- label: What should this vehicle be called in the menu?
        -- model: What is the spawn code for this vehicle?
        -- price: How much should it cost to rent? (Make price `0` if you want to rent that vehicle for free)
        -- image: What should be the preview image of the vehicle? (put in web/assets/images/rental) (Optional)
        { label = 'Scorcher', model = 'scorcher', price = 150, image = 'scorcher.webp'},
        { label = 'Bati 800', model = 'bati',     price = 350, image = 'bati.webp'},
        { label = 'XLS',      model = 'xls',      price = 650, image = 'xls.webp'},
    }
}


----------------------------------------
-- WARNING: DO NOT MODIFY BELOW THIS LINE
----------------------------------------
lib.locale()

_debug = function(...)
    local args = {...}
    for i, v in ipairs(args) do
        args[i] = tostring(v)
    end
    local message = table.concat(args, " ")
    print("^6[DEBUG] ^7" .. message)
end

_error = function(...)
    local args = {...}
    for i, v in ipairs(args) do
        args[i] = tostring(v)
    end
    local message = table.concat(args, " ")
    print("^1[ERROR] ^7" .. message)
end

cutscene, custom = {}, {}
```
{% endtab %}

{% tab title="open.lua" %}
```lua
-- Do you want to do something when the cutscene starts?
function cutscene.onStarted()
    -- Do something here
    -- Example:
    -- hideHud()

    -- If you have qb-apartment and with starting apartment enabled, remove the -- from the next line (i.e. remove the -- from line 8 and 9)
    -- bridge.menu.close()
    -- TriggerEvent("eh_cutscene:client:resetApartment")
end

-- Do you want to do something when the cutscene ends?
function cutscene.onEnded()
    -- Do something here
    -- Example:
    -- showHud()
    -- showGuidebook()
end

-- Do you want to fasten/unfasten the seatbelt for taxi rides as few servers has eject feature?
function cutscene.toggleSeatbelt(beltOn)
    if beltOn then
        -- Add your custom toggle seatbelt function here to fasten the belt
    else
        -- Add your custom toggle seatbelt function here tp unfasten the belt
    end
end

---------------------------------------------------
--- Custom Functions
---------------------------------------------------
function custom.sendMail(message, subject, sender)
    -- Add your custom mail function here i.e. phone
end

function custom.addVehicleKeys(plate, vehicle)
    -- Add your custom add vehicle keys function here
end

function custom.removeVehicleKeys(plate, vehicle)
-- Add your custom remove vehicle keys function here
end

function custom.showTextUI(text, position)
    -- Add your custom show text ui function here
    -- position: by default its `left`
end

function custom.hideTextUI()
    -- Add your custom hide text ui function here
end

function custom.setFuel(veh, amount)
    -- Add your custom set fuel function here
end

function custom.getFuel(veh)
    -- Add your custom get fuel function here
end
```
{% endtab %}
{% endtabs %}
