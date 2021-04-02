# aimware libraries

--region renderer
Copy and paste this inside of your lua script at the first line.

local Library_INSTALLED = false;
local Library_REWRITE = false;
file.Enumerate(function(filename)
    if filename == "Libraries/GraphicLib.lua" then
        Library_REWRITE = true;
        Library_INSTALLED = true;
    end;
end)
if not Library_INSTALLED or Library_REWRITE then
    local body = http.Get("https://raw.githubusercontent.com/BigGoosie/Aimware-GraphicLib/main/GraphicLib.lua");
    file.Write("Libraries/GraphicLib.lua", body);
end
RunScript("Libraries/GraphicLib.lua");
Parameters
