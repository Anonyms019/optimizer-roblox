-- Nome interno do script: direito_autoral_do_yk
-- Otimização automática para celulares fracos
-- Criado por YK

local RunService = game:GetService("RunService")
local Lighting = game:GetService("Lighting")
local UserSettings = UserSettings():GetService("UserGameSettings")

-- Reduz qualidade gráfica
pcall(function()
	UserSettings.SavedQualityLevel = Enum.SavedQualitySetting.QualityLevel1
end)

-- Ajustes gerais
Lighting.GlobalShadows = false
Lighting.EnvironmentDiffuseScale = 0
Lighting.EnvironmentSpecularScale = 0

-- Reduz distância de renderização
workspace.FogStart = 5
workspace.FogEnd = 60

-- Desativa partículas pesadas
for _, v in ipairs(workspace:GetDescendants()) do
	if v:IsA("ParticleEmitter") or v:IsA("Trail") then
		v.Enabled = false
	end
end

-- Desativa reflexos da água
workspace.Terrain.WaterReflection = false
workspace.Terrain.WaterWaveSize = 0
workspace.Terrain.WaterWaveSpeed = 0

-- Otimização contínua (limita FPS e carga)
RunService:Set3dRenderingEnabled(true)

-- Mensagem opcional para debug
print("⚡ Otimização direito_autoral_do_yk ativada!")
