# List of action

## Formula

```powerfx
fxCurrentUser = User();;
fxTheme = {
    primaryColorHEX: "#1b365f";
    secondaryColorHex: "#EED58E";
    greyControlHex: "#F6F6F4";
    greenControlHex: "#2b9348";
    redControlHex: "#c1121f";
    orangeControlHex: "#ffbf81"
};;
fxGUIDTJMCIOTeam = GUID(
    LookUp(
        'Environment Variable Values';
        'Environment Variable Definition'.'Schema Name' = "144957_tjm_guidteamadmin"
    ).Value
);;
fxCurrentDataverseUser = LookUp(
    Users;
    'Azure AD Object ID' = GUID(fxCurrentUser.EntraObjectId)
);;
fxCurrentTeamsUser = ShowColumns(
    fxCurrentDataverseUser.'Teams (teammembership_association)';
    Team
);;

```
