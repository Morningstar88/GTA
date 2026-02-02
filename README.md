# GTA

Zero

Attn Securityy Team. New repo here. 

Hey, intro to modding GTA asi files plz. What if I want to create a mod of Ubon, Thailand, directed by Kevin Smith, with a Clerks cast, pink-purple skies, and ScarJo as a friend. 

How would that be expressed in C++, C sharp etc... 

Cheers

*

C++

#include <windows.h>
#include "plugin.h"  // GTA plugin SDK

// Entry point when the game loads the ASI
BOOL APIENTRY DllMain(HMODULE hModule, DWORD ul_reason_for_call, LPVOID lpReserved) {
    if (ul_reason_for_call == DLL_PROCESS_ATTACH) {
        plugin::log("Ubon Thailand Mod loaded!");
        // Example: change sky color
        SetSkyColor(255, 100, 200); // pink-purple RGB
        // Example: spawn Clerks cast NPCs
        SpawnNPC("Dante", {100.0f, 200.0f, 20.0f});
        SpawnNPC("Randal", {102.0f, 200.0f, 20.0f});
        SpawnNPC("ScarJo", {105.0f, 200.0f, 20.0f});
    }
    return TRUE;
}

C Sharp

using GTA;
using GTA.Native;
using GTA.Math;

public class UbonMod : Script
{
    public UbonMod()
    {
        Tick += OnTick;
    }

    private void OnTick(object sender, EventArgs e)
    {
        // Change sky tint
        Function.Call(Hash.SET_WEATHER_TYPE_NOW, "EXTRASUNNY");
        World.CurrentDayTime = new TimeSpan(18, 30, 0); // sunset pink skies

        // Spawn Clerks cast
        Ped dante = World.CreatePed(PedHash.Business01AMM, new Vector3(100, 200, 20));
        Ped randal = World.CreatePed(PedHash.Business02AMM, new Vector3(102, 200, 20));
        Ped scarjo = World.CreatePed(PedHash.FilmDirector, new Vector3(105, 200, 20));
    }
}

Very cool. Deeper into C++ vs C# plz. What are hooks? Where are we pulling the ScarJo and Kevin Smith data from, normally? Plz tell me anything you think I need. 70 conceptual for now. I know a fair bit of front end, BTW, so analogies with JS etc can help, if its not too contrived. 
