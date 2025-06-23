--[[ LYMM Premium Script Loader ]]
-- Loader by Lymm — Hidden main script, proteksi premium

local PASSWORD = "Premium 30 Day"
local EXPIRE_TS = 1753304217 -- 23 Juli 2025

-- Check Expired
if os.time() > EXPIRE_TS then
    return game.Players.LocalPlayer:Kick("⚠️ Script Expired! Contact LYMM for renewal.")
end

-- Play Sound Intro (Default)
pcall(function()
    local s = Instance.new("Sound", game:GetService("SoundService"))
    s.SoundId = "rbxassetid://9118971971" -- efek suara opening
    s:Play()
end)

-- Show Loading GUI Animation
local lg = Instance.new("ScreenGui", game.Players.LocalPlayer:WaitForChild("PlayerGui"))
local fr = Instance.new("Frame", lg)
fr.Size = UDim2.new(1,0,1,0)
fr.BackgroundColor3 = Color3.new(0,0,0)
local txt = Instance.new("TextLabel", fr)
txt.Text = "🔥 Welcome to LYMM Premium Script 🔥"
txt.TextColor3 = Color3.fromRGB(255, 170, 0)
txt.Font = Enum.Font.Arcade
txt.TextScaled = true
txt.BackgroundTransparency = 1
txt.AnchorPoint = Vector2.new(0.5,0.5)
txt.Position = UDim2.new(0.5,0.4,0.5,0)
local pr = Instance.new("TextLabel", fr)
pr.Text = "Loading..."
pr.TextColor3 = Color3.fromRGB(255,255,255)
pr.Font = Enum.Font.SourceSans
pr.TextScaled = true
pr.BackgroundTransparency = 1
pr.AnchorPoint = Vector2.new(0.5,0.5)
pr.Position = UDim2.new(0.5,0.6,0.5,0)

-- Simulate loading progress
spawn(function()
    for i = 1, 5 do
        pr.Text = "Loading" .. string.rep(".", i)
        wait(0.5)
    end
    lg:Destroy()
    passwordUI()
end)

-- Obfuscated Password UI & Script Load
function passwordUI()
    local g=Instance.new("ScreenGui",game.Players.LocalPlayer:WaitForChild("PlayerGui"))
    local f=Instance.new("Frame",g)
    f.Size=UDim2.new(0,300,0,140)
    f.Position=UDim2.new(0.35,0,0.35,0)
    f.BackgroundColor3=Color3.fromRGB(25,25,25)
    f.BorderSizePixel=0
    local t=Instance.new("TextLabel",f)
    t.Text="🔐 Enter Premium Password"
    t.Size=UDim2.new(1,0,0.3,0)
    t.TextColor3=Color3.new(1,1,1)
    t.Font=Enum.Font.GothamBold
    t.TextScaled=true
    t.BackgroundTransparency=1
    local tb=Instance.new("TextBox",f)
    tb.PlaceholderText="Password"
    tb.Size=UDim2.new(0.9,0,0.25,0)
    tb.Position=UDim2.new(0.05,0,0.4,0)
    tb.Text=""
    tb.TextColor3=Color3.fromRGB(200,200,200)
    tb.BackgroundColor3=Color3.fromRGB(40,40,40)
    local btn=Instance.new("TextButton",f)
    btn.Text="🔓 LOGIN"
    btn.Size=UDim2.new(0.5,0,0.2,0)
    btn.Position=UDim2.new(0.25,0,0.7,0)
    btn.BackgroundColor3=Color3.fromRGB(0,120,0)
    btn.TextScaled=true
    btn.TextColor3=Color3.new(1,1,1)
    
    btn.MouseButton1Click:Connect(function()
        if tb.Text==PASSWORD then
            g:Destroy()
            loadMain()
        else
            game.Players.LocalPlayer:Kick("❌ Password incorrect! Script locked.")
        end
    end)
end

-- Main script loader (hidden/obfuscated)
function loadMain()
    -- Obfuscate key checks
    local z = "a"; local y = "b"
    local h = "c"..z; local w = "d"..y
    if #h + #w < 1 then end

    -- Fetch & execute hidden script
    loadstring(game:HttpGet("https://yourserver.com/ym2?x="..os.time()))()
end
