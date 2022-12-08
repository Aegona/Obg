local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("AEGON HUB", "GrapeTheme")
local Tab = Window:NewTab("Farm")
local Tab2 = Window:NewTab("Player")
local Section = Tab:NewSection("-- Farm Menu --")
local Section2 = Tab2:NewSection("My Body")

Section:NewToggle("Auto Sell BitCoin Oniy", "Sell BitCoin", function(f)
    _G.SellBit = f
while _G.SellBit do wait()


local args = {
    [1] = true
}

game:GetService("ReplicatedStorage").Events.ExchangeMoney:FireServer(unpack(args))
wait(3)
end
end)

Section:NewToggle("Auto Sell S ", "Sell S", function(f)
    _G.SellS = f
while _G.SellS do wait()

local args = {
    [1] = false
}

game:GetService("ReplicatedStorage").Events.ExchangeMoney:FireServer(unpack(args))

wait(3)
end
end)

Section:NewToggle("Auto Get Stars ดาว", "", function(f)
_G.Stars = f
while _G.Stars do wait()
game:GetService("ReplicatedStorage").Events.ClaimFreeBoostStar:FireServer()
wait(3)
end
end)


Section:NewToggle("Auto Get Box", "", function(f)
    _G.getbox = f
while _G.getbox do wait()
local args = {
    [1] = true
}

game:GetService("ReplicatedStorage").Events.ClmFrCrt:FireServer(unpack(args))
wait(3)
end
end)

Section:NewToggle("Auto open Box 600", "", function(f)
    _G.open600 = f
while _G.open600 do wait()
local args = {
    [1] = "Level 600 Crate"
}

game:GetService("ReplicatedStorage").Events.OpenCase:InvokeServer(unpack(args))
wait(3)
end
end)


Section:NewButton("anti AFK", "AFK", function()
local vu = game:GetService("VirtualUser")
	game:GetService("Players").LocalPlayer.Idled:connect(function()
		vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
		wait(1)
		vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
	end)
end)


Section2:NewSlider("WalkSpeed", "WalkSpeed", 500, 16, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
