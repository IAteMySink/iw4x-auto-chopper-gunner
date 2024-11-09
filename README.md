
-Credits-

This is the Autonomous Chopper Gunner Mod for the IW4x Client made by IAteMySink.

Q&A:

What does this mod do?
It makes the Chopper Gunner operate on its own rather than you controlling it. It now lasts 60 seconds (check docs if you want to revert to 40) and it borrows logic from the Cobra to use accurate targeting and decimate anyone in sight (excluding those with the cold-blooded perk, that is.) All functions remain intact. It has its original, aggressive flight path, a set of flares, and now even shoots the occasional missile the same way the Cobra does.

Is it compatible with (insert other mod here) mod!?
Yes, only a few files are edited. This will be compatible with any mod that doesn't directly edit killstreak scripts like H3X1C's killstreak fixes or cpt.price141's custom killstreaks. It will work fine with INeedGame's Bot Mod and most other misc. mods.

As a fun treat, this mod doesn't replace the cobra_player_minigun_mp weapon (Chopper Gunner's Turret) with means you can do stupid things like attach the AC130's 25mm or 40mm cannons to it lol



--------DOCS--------

If you're just wanting to play with the mod, you can ignore this. This is just a list of edits made to the scripts for the sake of editing and messing around as you wish. (tip: CTRL+F and search things in quotations here in the scripts to locate changes quickly)





Edits made to stock _helicopter.gsc:

-added new "level.chopper_turretClipSize" variable for Chopper Gunner infinite clip

-in "heli_think", disable threading "heliride" for no player-control. in switch "helitype", change duration to 60 seconds, thread a new set of attack targets logic for Chopper Gunner, ("attack_targets_chopper",threading "attack_primary_chopper") and thread the splash card that was normally in heliride

-"attack_primary_chopper" is just an alternate version (of "attack_primary") with changes that make it have the chopper gunner turret, as well as a separate secondary missile firing. Both have their own threaded branches of code for these things (with "_chopper" as a suffix).

-in "tryUseHelicopter", add "minigun" type so Chopper Gunner goes into heli queue, and disable minigun type threading with "null" so that there is no threading from _killstreaks.gsc. Also added a "switchtolastweapon" to have the computer close itself.

-in "useHelicopterMinigun", removed inability to use during Last Stand because it's just being deployed like other Helis.





Edits made to stock _killstreak.gsc:

-change "isRideKillstreak" to not include Chopper Gunner





Edits made to stock _damage.gsc:

-in "handleNormalDeath", moved "cobra_player_minigun_mp" to the non-rideables section (Killstreak doesn't persist increasing killstreak in future lives)




If all else (this doc) fails when searching for edits, use something (Notepad++ maybe) to compare the gsc's of this mod with the original file(s) in IW4x.
