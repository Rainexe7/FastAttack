local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if _G.FastAttack then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end

spawn(function()
    while _G.FastAttack do task.wait()
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    xShadowFastAttackx = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    xShadowx = debug.getupvalues(xShadowFastAttackx)[2]
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                if typeof(xShadowx) == "table" then
                    pcall(function()
                        xShadowx.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        xShadowx.activeController.timeToNextAttack = 0
                        xShadowx.activeController.hitboxMagnitude = 200
                        xShadowx.activeController.active = false
                        xShadowx.activeController.timeToNextBlock = 0
                        xShadowx.activeController.focusStart = 0
                        xShadowx.activeController.increment = 4
                        xShadowx.activeController.blocking = false
                        xShadowx.activeController.attacking = false
                        xShadowx.activeController.humanoid.AutoRotate = true
                    end)
                end
            end
        end
    end)
    
    local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
    local CombatFramework = debug.getupvalues(Module)[2]
    local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
    
    task.spawn(function()
        while true do task.wait()
            if _G.FastAttack then
                pcall(function()
                    CameraShakerR:Stop()
                    CombatFramework.activeController.attacking = false
                    CombatFramework.activeController.timeToNextAttack = 0
                    CombatFramework.activeController.increment = 4
                    CombatFramework.activeController.hitboxMagnitude = 100
                    CombatFramework.activeController.blocking = false
                    CombatFramework.activeController.timeToNextBlock = 0
                    CombatFramework.activeController.focusStart = 0
                    CombatFramework.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
    
    local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
    local VirtualUser = game:GetService('VirtualUser')
    local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
    local Client = game:GetService("Players").LocalPlayer
    local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)
    
    function SeraphFuckWeapon() 
        local p13 = SeraphFrame.activeController
        local wea = p13.blades[1]
        if not wea then return end
        while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
        return wea
    end
    
    function getHits(Size)
        local Hits = {}
        local Enemies = workspace.Enemies:GetChildren()
        local Characters = workspace.Characters:GetChildren()
        for i=1,#Enemies do local v = Enemies[i]
            local Human = v:FindFirstChildOfClass("Humanoid")
            if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                table.insert(Hits,Human.RootPart)
            end
        end
        for i=1,#Characters do local v = Characters[i]
            if v ~= game.Players.LocalPlayer.Character then
                local Human = v:FindFirstChildOfClass("Humanoid")
                if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
                    table.insert(Hits,Human.RootPart)
                end
            end
        end
        return Hits
    end
    
    task.spawn(
        function()
        while true do task.wait()
            if  _G.FastAttack then
                if SeraphFrame.activeController then
                    if v.Humanoid.Health > 0 then
                        SeraphFrame.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                        SeraphFrame.activeController.timeToNextAttack = 0
                        SeraphFrame.activeController.focusStart = 0
                        SeraphFrame.activeController.hitboxMagnitude = 110
                        SeraphFrame.activeController.humanoid.AutoRotate = true
                        SeraphFrame.activeController.increment = 4
                    end
                end
            end
        end
    end)
    
    function Boost()
        spawn(function()
            if SeraphFrame.activeController then
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
            end
        end)
    end
    
    function Unboost()
        spawn(function()
            --print("Unboost ของจริง555")
            --game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
        end)
    end
    
    local cdnormal = 0
    local Animation = Instance.new("Animation")
    local CooldownFastAttack = 0.000000
    Attack = function()
        local ac = SeraphFrame.activeController
        if ac and ac.equipped then
            task.spawn(
                function()
                if tick() - cdnormal > 0 then
                    ac:attack()
                    cdnormal = tick()
                else
                    Animation.AnimationId = ac.anims.basic[2]
                    ac.humanoid:LoadAnimation(Animation):Play(0.01, 0.01) --ท่าไม่ทำงานแก้เป็น (1,1)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(60), 1, "")
                end
                wait(0.12)
            end)
        end
    end
    
    b = tick()
    spawn(function()
        while _G.FastAttack do task.wait()
            if _G.FastAttack then
                if b - tick() > 9e9 then
                    b = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Attack()
                                wait()
                                Boost()
                            end
                        end
                    end
                end)
                wait(0.05)
            end
        end
    end)
    
    k = tick()
    spawn(function()
        while wait() do
            if  _G.FastAttack then
                if k - tick() > 9e9 then
                    k = tick()
                end
                pcall(function()
                    for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 90 then
                                Unboost()
                            end
                        end
                    end
                end)
            end
        end
    end)
    
    tjw1 = true
    task.spawn(
        function()
            local a = game.Players.LocalPlayer
            local b = require(a.PlayerScripts.CombatFramework.Particle)
            local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
            if not shared.orl then
                shared.orl = c.wrapAttackAnimationAsync
            end
            if not shared.cpc then
                shared.cpc = b.play
            end
            if tjw1 then
                pcall(
                    function()
                        c.wrapAttackAnimationAsync = function(d, e, f, g, h)
                            local i = c.getBladeHits(e, f, g)
                            if i then
                                b.play = function()
                                end
                                d:Play(0.01,0.01,0.01)
                                h(i)
                                b.play = shared.cpc
                                wait(0.1)
                                d:Stop()
                            end
                        end
                    end
                )
            end
        end
    )
    
    local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}
    
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    task.spawn(function()
        pcall(function()
            if not shared.orl then
                shared.orl = STOPRL.wrapAttackAnimationAsync
            end
                if not shared.cpc then
                    shared.cpc = STOP.play 
                end
                spawn(function()
                    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
                    game:GetService("RunService").Stepped:Connect(function()
                        STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                            local Hits = STOPRL.getBladeHits(b,c,d)
                            if Hits then
                                if  _G.FastAttack then
                                    STOP.play = function() end
                                    a:Play(21,29,30)
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                else
                                    func(Hits)
                                    STOP.play = shared.cpc
                                    wait(a.length * 9e9)
                                    a:Stop()
                                end
                            end
                        end
                    end)
                end)
            end)
        end)
    end
end)

spawn(function()
		game:GetService("RunService").RenderStepped:Connect(function()
			if _G.FastAttackNormalSpeed == true then
				game.Players.LocalPlayer.Character.Stun.Value = 0
				game.Players.LocalPlayer.Character.Humanoid.Sit = false
				game.Players.LocalPlayer.Character.Busy.Value = false        
			end
		end)
	end)

	local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
	local VirtualUser = game:GetService('VirtualUser')
	local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
	local Client = game:GetService("Players").LocalPlayer
	local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)

	function SeraphFuckWeapon() 
		local p13 = SeraphFrame.activeController
		local wea = p13.blades[1]
		if not wea then return end
		while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
		return wea
	end

	function getHits(Size)
		local Hits = {}
		local Enemies = workspace.Enemies:GetChildren()
		local Characters = workspace.Characters:GetChildren()
		for i=1,#Enemies do local v = Enemies[i]
			local Human = v:FindFirstChildOfClass("Humanoid")
			if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
				table.insert(Hits,Human.RootPart)
			end
		end
		for i=1,#Characters do local v = Characters[i]
			if v ~= game.Players.LocalPlayer.Character then
				local Human = v:FindFirstChildOfClass("Humanoid")
				if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
					table.insert(Hits,Human.RootPart)
				end
			end
		end
		return Hits
	end

	spawn(
		function()
			while  task.wait() do
				if  _G.FastAttackNormalSpeed then
					if SeraphFrame.activeController then
						if v.Humanoid.Health > 0 then
							SeraphFrame.activeController.attacking = false
							SeraphFrame.activeController.timeToNextBlock = 0
							SeraphFrame.activeController.humanoid.AutoRotate = true
							SeraphFrame.activeController.increment = 3
							SeraphFrame.activeController.blocking = false
							SeraphFrame.activeController.hitboxMagnitude = 200
							SeraphFrame.activeController.timeToNextAttack = 0
							SeraphFrame.activeController.focusStart = 0
							SeraphFrame.activeController.humanoid.AutoRotate = true
							SeraphFrame.activeController.increment = 1 + 1 / 1
						end
					end
				end
			end
		end)

	function Boost()
		spawn(function()
			game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
		end)
	end

	function Unboost()
		spawn(function()
			game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
		end)
	end

	local cdnormal = 9e9
	local Animation = Instance.new("Animation")
	local CooldownFastAttack = 0
	Attack = function()
		local ac = SeraphFrame.activeController
		if ac and ac.equipped then
			task.spawn(
				function()
					if tick() - cdnormal > 9e9 then
						ac:attack()
						cdnormal = tick()
					else
						Animation.AnimationId = ac.anims.basic[2]
						ac.humanoid:LoadAnimation(Animation):Play(100, 99) --à¸—à¹ˆà¸²à¹„à¸¡à¹ˆà¸—à¸³à¸‡à¸²à¸™à¹à¸à¹‰à¹€à¸›à¹‡à¸™ (1,1)
						game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(120), 2, "")
					end
				end)
		end
	end

	b = tick()
	spawn(function()
		while  task.wait() do
			if  _G.FastAttackNormalSpeed then
				if b - tick() > 0.75 then
					task.wait()
					b = tick()
				end
				pcall(function()
					for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
						if v.Humanoid.Health > 0 then
							if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
								Attack()
								task.wait()
								Boost()
							end
						end
					end
				end)
			end
		end
	end)

	k = tick()
	spawn(function()
		while  task.wait() do
			if  _G.FastAttackNormalSpeed then
				if k - tick() > 0.75 then
					task.wait()
					k = tick()
				end
				pcall(function()
					for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
						if v.Humanoid.Health > 0 then
							if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 40 then
								task.wait()
								Unboost()
							end
						end
					end
				end)
			end
		end
	end)

	tjw1 = true
	spawn(
		function()
			local a = game.Players.LocalPlayer
			local b = require(a.PlayerScripts.CombatFramework.Particle)
			local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
			if not shared.orl then
				shared.orl = c.wrapAttackAnimationAsync
			end
			if not shared.cpc then
				shared.cpc = b.play
			end
			if tjw1 then
				pcall(
					function()
						c.wrapAttackAnimationAsync = function(d, e, f, g, h)
							local i = c.getBladeHits(e, f, g)
							if i then
								b.play = function()
								end
								d:Play(15.25, 15.25, 15.25)
								h(i)
								b.play = shared.cpc
								task.wait()
								d:Stop()
							end
						end
					end
				)
			end
		end
	)

	local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)

	CombatFrameworkR = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)

	y = debug.getupvalues(CombatFrameworkR)[2]

	spawn(function()

		game:GetService("RunService").RenderStepped:Connect(function()

			if _G.FastAttackNormalSpeed then

				if typeof(y) == "table" then

					pcall(function()

						CameraShaker:Stop()

						y.activeController.timeToNextAttack = (math.huge^math.huge^math.huge)

						y.activeController.timeToNextAttack = 0

						y.activeController.hitboxMagnitude = 60

						y.activeController.active = false

						y.activeController.timeToNextBlock = 0

						y.activeController.focusStart = 1655503339.0980349

						y.activeController.increment = 0

						y.activeController.blocking = false

						y.activeController.attacking = false

						y.activeController.humanoid.AutoRotate = true

					end)

				end

			end

		end)

	end)

	local plr = game.Players.LocalPlayer

	local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
	local CbFw2 = CbFw[2]

	function GetCurrentBlade() 
		local p13 = CbFw2.activeController
		local ret = p13.blades[1]
		if not ret then return end
		while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
		return ret
	end

	function AttackNoCD() 
		local AC = CbFw2.activeController
		for i = 1, 1 do 
			local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
			plr.Character,
			{plr.Character.HumanoidRootPart},
			30
			)
			local cac = {}
			local hash = {}
			for k, v in pairs(bladehit) do
				if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
					table.insert(cac, v.Parent.HumanoidRootPart)
					hash[v.Parent] = true
				end
			end
			bladehit = cac
			if #bladehit > 0 then
				local u8 = debug.getupvalue(AC.attack, 3)
				local u9 = debug.getupvalue(AC.attack, 4)
				local u7 = debug.getupvalue(AC.attack, 6)
				local u10 = debug.getupvalue(AC.attack, 7)
				local u12 = (u8 * 20 + u7 * 27) % u9
				local u13 = u7 * 27
				(function()
					u12 = (u12 * u9 + u13) % 10
					u8 = math.floor(u12 / u9)
					u7 = u12 - u8 * u9
				end)()
				u10 = u10 + 0
				debug.setupvalue(AC.attack, 3, u8)
				debug.setupvalue(AC.attack, 4, u9)
				debug.setupvalue(AC.attack, 6, u7)
				debug.setupvalue(AC.attack, 7, u10)
				pcall(function()
					for k, v in pairs(AC.animator.anims.basic) do
						v:Play(10, 10, 10)
					end                  
				end)
				if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
					game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
				end
			end
		end
	end
	spawn(function()
		while wait(.2) do
			if _G.FastAttackNormalSpeed then
			end
		end
	end)

	local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
	CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}

	local Client = game.Players.LocalPlayer
	local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
	local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
	spawn(function()
		pcall(function()
			if not shared.orl then
				shared.orl = STOPRL.wrapAttackAnimationAsync
			end
			if not shared.cpc then
				shared.cpc = STOP.play 
			end
			spawn(function()
				require(game.ReplicatedStorage.Util.CameraShaker):Stop()
				require(game.ReplicatedStorage.Util.CameraShaker):Stop()
				game:GetService("RunService").Stepped:Connect(function()
					STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
						local Hits = STOPRL.getBladeHits(b,c,d)
						if Hits then
							if  _G.FastAttackNormalSpeed then
								STOP.play = function() end
								a:Play(20.1,15.1,10.1)
								func(Hits)
								STOP.play = shared.cpc
								wait(a.length * .0)
								a:Stop()
							else
								func(Hits)
								STOP.play = shared.cpc
								wait(a.length * .0)
								a:Stop()
							end
						end
					end
				end)
			end)
		end)
	end)


	local SeraphFrame = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework")))[2]
	local VirtualUser = game:GetService('VirtualUser')
	local RigControllerR = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.RigController))[2]
	local Client = game:GetService("Players").LocalPlayer
	local DMG = require(Client.PlayerScripts.CombatFramework.Particle.Damage)

	function SeraphFuckWeapon() 
		local p13 = SeraphFrame.activeController
		local wea = p13.blades[1]
		if not wea then return end
		while wea.Parent~=game.Players.LocalPlayer.Character do wea=wea.Parent end
		return wea
	end

	function getHits(Size)
		local Hits = {}
		local Enemies = workspace.Enemies:GetChildren()
		local Characters = workspace.Characters:GetChildren()
		for i=1,#Enemies do local v = Enemies[i]
			local Human = v:FindFirstChildOfClass("Humanoid")
			if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
				table.insert(Hits,Human.RootPart)
			end
		end
		for i=1,#Characters do local v = Characters[i]
			if v ~= game.Players.LocalPlayer.Character then
				local Human = v:FindFirstChildOfClass("Humanoid")
				if Human and Human.RootPart and Human.Health > 0 and game.Players.LocalPlayer:DistanceFromCharacter(Human.RootPart.Position) < Size+55 then
					table.insert(Hits,Human.RootPart)
				end
			end
		end
		return Hits
	end

	spawn(
		function()
			while task.wait() do
				if  _G.FastAttackNormalSpeed then
					if SeraphFrame.activeController then
						if v.Humanoid.Health > 0 then
							SeraphFrame.activeController.timeToNextAttack = 2
							SeraphFrame.activeController.focusStart = 0
							SeraphFrame.activeController.hitboxMagnitude = 200
							SeraphFrame.activeController.humanoid.AutoRotate = true
							SeraphFrame.activeController.increment = 3 + 3 / 3
						end
					end
				end
			end
		end)

	function Boost()
		spawn(function()
			game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(SeraphFuckWeapon()))
		end)
	end

	function Unboost()
		spawn(function()
			game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("unequipWeapon",tostring(SeraphFuckWeapon()))
		end)
	end

	local cdnormal = 9e9
	local Animation = Instance.new("Animation")
	local CooldownFastAttack = 0
	Attack = function()
		local ac = SeraphFrame.activeController
		if ac and ac.equipped then
			task.spawn(
				function()
					if tick() - cdnormal > 9e9 then
						ac:attack()
						cdnormal = tick()
					else
						Animation.AnimationId = ac.anims.basic[2]
						ac.humanoid:LoadAnimation(Animation):Play(0, 0) --ท่าไม่ทำงานแก้เป็น (1,1)
						game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", getHits(120), 2, "")
					end
				end)
		end
	end

	b = tick()
	spawn(function()
		while _G.FastAttackNormalSpeed do
			if _G.FastAttackNormalSpeed then
				if b - tick() > 9e9 then
					b = tick()
				end
				pcall(function()
					for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
						if v.Humanoid.Health > 0 then
							if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
								Attack()
								task.wait()
								Boost()
							end
						end
					end
				end)
			end
		end
	end)

	k = tick()
	spawn(function()
		while  task.wait() do
			if  _G.FastAttackNormalSpeed then
				if k - tick() > 9e9 then
					k = tick()
				end
				pcall(function()
					for i, v in pairs(game.Workspace.Enemies:GetChildren()) do
						if v.Humanoid.Health > 0 then
							if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 50 then
								Unboost()
							end
						end
					end
				end)
			end
		end
	end)

	tjw1 = true
	spawn(
		function()
			local a = game.Players.LocalPlayer
			local b = require(a.PlayerScripts.CombatFramework.Particle)
			local c = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
			if not shared.orl then
				shared.orl = c.wrapAttackAnimationAsync
			end
			if not shared.cpc then
				shared.cpc = b.play
			end
			if tjw1 then
				pcall(
					function()
						c.wrapAttackAnimationAsync = function(d, e, f, g, h)
							local i = c.getBladeHits(e, f, g)
							if i then
								b.play = function()
								end
								d:Play(25.25, 20.25, 23)
								h(i)
								b.play = shared.cpc
								wait(9e9)
								d:Stop()
							end
						end
					end
				)
			end
		end
	)


	function AttackFunction()
		local ac = CombatFrameworkR.activeController
		if ac and ac.equipped then
			for indexincrement = 1, 1 do
				local bladehit = getAllBladeHits(60)
				if #bladehit > 0 then
					local AcAttack8 = debug.getupvalue(ac.attack, 5)
					local AcAttack9 = debug.getupvalue(ac.attack, 6)
					local AcAttack7 = debug.getupvalue(ac.attack, 4)
					local AcAttack10 = debug.getupvalue(ac.attack, 7)
					local NumberAc12 = (AcAttack8 * 798405 + AcAttack7 * 727595) % AcAttack9
					local NumberAc13 = AcAttack7 * 798405
					(function()
						NumberAc12 = (NumberAc12 * AcAttack9 + NumberAc13) % 1099511627776
						AcAttack8 = math.floor(NumberAc12 / AcAttack9)
						AcAttack7 = NumberAc12 - AcAttack8 * AcAttack9
					end)()
					AcAttack10 = AcAttack10 + 1
					debug.setupvalue(ac.attack, 5, AcAttack8)
					debug.setupvalue(ac.attack, 6, AcAttack9)
					debug.setupvalue(ac.attack, 4, AcAttack7)
					debug.setupvalue(ac.attack, 7, AcAttack10)
					for k, v in pairs(ac.animator.anims.basic) do
						v:Play(20,10.01,10)
					end                 
					if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") and ac.blades and ac.blades[1] then 
						game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(CurrentWeapon()))
						game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(NumberAc12 / 1099511627776 * 16777215), AcAttack10)
						game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, 2, "") 
					end
				end
			end
		end
	end

	local CameRa = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
	CameRa.CameraShakeInstance.CameraShakeState = {FadingIn = 3,FadingOut = 2,Sustained = 0,Inactive =1}

	local Client = game.Players.LocalPlayer
	local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
	local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
	spawn(function()
		pcall(function()
			if not shared.orl then
				shared.orl = STOPRL.wrapAttackAnimationAsync
			end
			if not shared.cpc then
				shared.cpc = STOP.play 
			end
			spawn(function()
				require(game.ReplicatedStorage.Util.CameraShaker):Stop()
				require(game.ReplicatedStorage.Util.CameraShaker):Stop()
				game:GetService("RunService").Stepped:Connect(function()
					STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
						local Hits = STOPRL.getBladeHits(b,c,d)
						if Hits then
							if  _G.FastAttackNormalSpeed then
								STOP.play = function() end
								a:Play(21,29,30)
								func(Hits)
								STOP.play = shared.cpc
								wait(a.length * 0)
								a:Stop()
							else
								func(Hits)
								STOP.play = shared.cpc
								wait(a.length * 0)
								a:Stop()
							end
						end
					end
				end)
			end)
		end)
	end)
