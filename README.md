- š Hi, Iām @whyhaveaname
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
whyhaveaname/whyhaveaname is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
; #Warn  ; Enable warnings to assist with detecting common errors.
SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
SetWorkingDir %A_ScriptDir%  ; Ensures a consistent starting directory.

;OPTIMIZATIONS START
#MaxHotkeysPerInterval 99000000
#HotkeyInterval 99000000
#KeyHistory 0
ListLines Off
Process, Priority, , A
SetBatchLines, -1
SetKeyDelay, -1, -1
SetMouseDelay, -1
SetDefaultMouseSpeed, 0
SetWinDelay, -1
SetControlDelay, -1
;OPTIMIZATIONS END

CoordMode, Mouse, Screen 
CoordMode, Pixel, Screen 
color = 0x433C6D
MidX := A_ScreenWidth / 2 
MidY := A_ScreenHeight / 2 
Triggerbot = 1 
Sense = 2

~RButton::
{
	While GetKeyState("RButton"){
PixelSearch, TargetX, TargetY, 0, 0, %A_ScreenWidth%, %A_ScreenHeight%, %color%, 5, Fast
If ErrorLevel = 0 
{ 
MoveX := ((TargetX - MidX) / sense) 
MoveY := ((TargetY - MidY) / sense) 
MouseMove, MoveX, MoveY,, R 
if (TriggerBot = 1) 
Click 
}
}
}
return

`::exitapp
