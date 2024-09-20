- JSON web tokens enable a secure way to transmit data between two parties in the form of a JSON object.
- JSON web tokens consist of three basic parts: the header, the payload, and the signature.
- According to the configuration, the token is going to be valid if: 
  1- The issuer is the actual server that created the token (ValidateIssuer=true) 
  2- The receiver of the token is a valid recipient (ValidateAudience=true) 
  3- The token has not expired (ValidateLifetime=true)  The signing key is valid and is trusted by the server (ValidateIssuerSigningKey=true)