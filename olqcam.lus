local frame = CreateFrame("Frame");
frame:RegisterEvent("ADDON_LOADED");
frame:RegisterEvent("CHAT_MSG_SYSTEM");
frame:RegisterEvent("PLAYER_LEAVING_WORLD");
frame:SetScript("OnEvent", function(self, event, arg)
	if event=="ADDON_LOADED" then
		SetCVar("cameraYawMoveSpeed","230");
	elseif event=="PLAYER_LEAVING_WORLD" then
		MoveViewRightStop();
		SetCVar("cameraYawMoveSpeed","230");
		SetView(5);
	elseif event=="CHAT_MSG_SYSTEM" then
		if (arg == format(MARKED_AFK_MESSAGE,DEFAULT_AFK_MESSAGE) and GetCVar("autoClearAFK") == "1") then
			UIParent:Hide();
			SetView(3);
			SetCVar("cameraYawMoveSpeed","8");
			MoveViewRightStart();
		elseif arg == CLEARED_AFK then
			UIParent:Show();
			MoveViewRightStop();
			SetCVar("cameraYawMoveSpeed","230");
			SetView(5);
		end
	end
end);