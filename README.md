
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local gui = Instance.new("ScreenGui")
gui.Name = "RenatoHub"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local open = Instance.new("TextButton")
open.Size = UDim2.new(0, 55, 0, 55)
open.Position = UDim2.new(0, 15, 0.5, -27)
open.Text = "R"
open.TextSize = 25
open.Parent = gui

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 230, 0, 300)
frame.Position = UDim2.new(0.5, -115, 0.5, -150)
frame.BackgroundTransparency = 0.1
frame.Visible = false
frame.Parent = gui

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 50)
title.Text = "RENATO HUB"
title.TextSize = 24
title.Parent = frame

local funcoes = {
    "Buy Space",
    "Sorte ao Girar",
    "Girar Fruta Free",
    "Hall Free"
}

for i, nome in ipairs(funcoes) do
    local button = Instance.new("TextButton")
    button.Size = UDim2.new(1, -20, 0, 45)
    button.Position = UDim2.new(0, 10, 0, 55 + (i - 1) * 55)
    button.Text = nome
    button.TextSize = 18
    button.Parent = frame

    button.MouseButton1Click:Connect(function()
        button.Text = "✓ " .. nome
        task.wait(0.8)
        button.Text = nome
    end)
end

open.MouseButton1Click:Connect(function()
    frame.Visible = not frame.Visible
end)
