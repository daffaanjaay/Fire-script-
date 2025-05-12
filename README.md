-- FireEffectScript di ServerScriptService
local fireEffect = game.ReplicatedStorage:WaitForChild("FireEffect")

-- Fungsi untuk memunculkan efek api di tubuh pemain
local function spawnFire(player)
    local character = player.Character
    if character and character:FindFirstChild("HumanoidRootPart") then
        -- Membuat api di tubuh pemain
        local fire = Instance.new("Fire")
        fire.Parent = character.HumanoidRootPart
        fire.Size = 10
        fire.Heat = 50
    end
end

-- Ketika RemoteEvent dipanggil, spawn api di tubuh pemain
fireEffect.OnServerEvent:Connect(spawnFire)
