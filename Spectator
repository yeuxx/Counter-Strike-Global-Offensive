
void CVisuals::SpecList()
{
	auto m_pLocalPlayer = reinterpret_cast<SDK::CBaseEntity*>(INTERFACES::ClientEntityList->GetClientEntity(INTERFACES::Engine->GetLocalPlayer()));

	RECT scrn = INTERFACES::Engine->GetViewport();
	int ayy = 0;
	int screen_width, screen_height;
	INTERFACES::Engine->GetScreenSize(screen_width, screen_height);
	for (int i = 0; i < INTERFACES::ClientEntityList->GetHighestEntityIndex(); i++)
		if (SETTINGS::settings.aa_bool)
		{
			SDK::CBaseEntity* entity = INTERFACES::ClientEntityList->GetClientEntity(i);
			SDK::player_info_t pinfo;

			if (entity &&  entity != m_pLocalPlayer)
			{
				if (INTERFACES::Engine->GetPlayerInfo(i, &pinfo) && !entity->IsAlive() && !entity->GetIsDormant())
				{
					HANDLE obs = entity->GetObserverModeHandle();

					if (obs)
					{
						SDK::CBaseEntity* pTarget = INTERFACES::ClientEntityList->GetClientEntity(i);
						SDK::player_info_t pinfo2;

						if (INTERFACES::Engine->GetPlayerInfo(pTarget->GetIndex(), &pinfo2))
						{
							char buf1[255];
							sprintf_s(buf1, "%s", pinfo.name);

							RENDER::DrawF(1890, screen_height - 1065 + (ayy * 10), FONTS::visuals_name_font, true, true, CColor(255, 255, 255, 255), buf1);

							ayy++;

						}
					}
				}
			}
		}
}
