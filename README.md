// Declare Token
var text Token = "dan226zdqg8db7dxu8i9hfje7nq";

// Create the URL to add a record to the Stakeholders Table
var text URLONE = URLRoot() & "db/" & [_DBID_STAKEHOLDERS] & "?a=API_AddRecord&_fid_42=" & URLEncode([Model ID#]) & "&apptoken=" & Token;

// Create the URL to add a record to the Risk Assessment Matrix Table
var text URLTWO = URLRoot() & "db/" & [_DBID_RISK_ASSESSMENT_MATRIX_2] & "?a=API_AddRecord&_fid_77=" & URLEncode([Model ID#]) & "&apptoken=" & Token;

// Chain URLs: Create the Stakeholders record, then the Risk Assessment Matrix record, then redirect to edit the new Risk Assessment Matrix record
$URLONE & "&rdr=" & URLEncode(
    $URLTWO & "&rdr=" & URLEncode(
        URLRoot() & "db/" & [_DBID_RISK_ASSESSMENT_MATRIX_2] & "?a=er&rid=" & URLEncode("rid")
    )
)
