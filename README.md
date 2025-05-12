-- Script Api (client-side) - KRNL, Delta, dll
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

-- Hapus api lama kalau ada
for _, part in pairs(character:GetDescendants()) do
    if part:IsA("Fire") then
        part:Destroy()
    end
end

-- Tambahkan efek api ke seluruh BasePart karakter
for _, part in pairs(character:GetDescendants()) do
    if part:IsA("BasePart") then
        local fire = Instance.new("Fire")
        fire.Size = 10
        fire.Heat = 25
        fire.Parent = part
    end
end

print("Efek api berhasil ditambahkan ke tubuhmu!")
