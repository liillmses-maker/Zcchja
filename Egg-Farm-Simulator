local shared = odh_shared_plugins

local flick_section = shared.AddSection("Flick to Murderer V3")

flick_section:AddLabel("Credits: @thanhtv68_ (Mồn Lèo)")

local flickEnabled = false
local flickDuration = 0.3
local autoShotEnabled = false
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local UIS = game:GetService("UserInputService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local murdererButton

local function findMurderer()
    if game.PlaceId == 142823291 then
        local success, roleData = pcall(function()
            local remote = ReplicatedStorage:FindFirstChild("GetPlayerData", true)
            if remote and remote:IsA("RemoteFunction") then
                return remote:InvokeServer()
            end
        end)
        if success and roleData then
            for playerName, data in pairs(roleData) do
                if data.Role == "Murderer" and not data.Killed and not data.Dead then
                    local p = Players:FindFirstChild(playerName)
                    if p then
                        return p
                    end
                end
            end
        end
        return nil
    else
        for _, player in ipairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
                local backpack = player:FindFirstChildOfClass("Backpack")
                if backpack and backpack:FindFirstChild("Knife") then
                    return player
                end
                for _, item in ipairs(player.Character:GetChildren()) do
                    if item:IsA("Tool") and item.Name == "Knife" then
                        return player
                    end
                end
            end
        end
        return nil
    end
end
-- my onlyfans: https://onlyfans.wtf/sqworexo
-- thank you
-- me gun: guus.lol/sqworexo
-- my github: liillmses-maker

local function shootGun()
    local char = LocalPlayer.Character
    if not char then return end
    local gun = char:FindFirstChild("Gun") or LocalPlayer.Backpack:FindFirstChild("Gun")
    if not gun then return end
    if gun.Parent == LocalPlayer.Backpack then
        LocalPlayer.Character.Humanoid:EquipTool(gun)
        task.wait(0.1)
    end
    local args = {0, Vector3.new(), "AH2"}
    local rf = gun:WaitForChild("KnifeLocal"):WaitForChild("CreateBeam"):WaitForChild("RemoteFunction")
    rf:InvokeServer(unpack(args))
end
