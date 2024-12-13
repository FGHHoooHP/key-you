local validKey = "keyez"

-- Check if the entered key is valid
if getgenv().key == validKey then
    -- Perform actions for valid key (e.g., show a message or enable features)
    print("Key valid!")
    -- You can replace this print with actions like displaying a UI, etc.
else
    -- Handle invalid key (e.g., kick the player)
    game.Players.LocalPlayer:Kick("Invalid key!")
end
