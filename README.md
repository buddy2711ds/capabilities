# capabilities
#include "wd_core.au3"  Local $sDesiredCapabilities  $_WD_DEBUG = False  SetupChrome() _WD_Startup() $sSession = _WD_CreateSession($sDesiredCapabilities) _WD_Navigate($sSession, "https://www.88countryclub.co.kr/") $hwnd = WinWaitActive("88") WinSetState($hwnd, "", @SW_MAXIMIZE)  Sleep(1000) ControlSend($hwnd, "", "", "^f")  Func SetupChrome() _WD_Option('Driver', 'chromedriver.exe') _WD_Option('Port', 9515) _WD_Option('DriverParams', '--log-path=' &amp; @ScriptDir &amp; '\chrome.log')  $sDesiredCapabilities = '{"capabilities": {"alwaysMatch": {"chromeOptions": {"w3c": true }}}}' EndFunc
