# Additional Notes

## Add an Enable SteelShield Flag

If you are planning to run your Game Servers in infrastructure that is not protected by SteelShield, it is advisable to
include a flag on the server component which indicates if the server is protected by SteelShield.

When the server starts up and sends its details to the games backend server list, it would include the
`SteelShieldEnabled` flag, which it can send to the client when the client queries the server list.

This way the client will know that it should be performing the SteelShield Token Request process and prepend the token
to network packets when in a SteelShield environment, or not do so in non SteelShield environments. 

Another option is to skip the token retrieval process via token service and to generate a pseudo token for environments 
where no SteelShield is actively used and therefore the network protocol code does not require any additional conditions/changes.
