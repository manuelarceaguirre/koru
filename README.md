// Declare Token
var text Token = "dan226zdqg8db7dxu8i9hfje7nq";

// Create the URL to add a record to the Stakeholders Table
var text URLONE = URLRoot() & "db/" & [_DBID_STAKEHOLDERS] & "?a=API_AddRecord&_fid_42=" & URLEncode([Model ID#]) & "&apptoken=" & Token;

// Create the URL to add a record to the Risk Assessment Matrix Table
var text URLTWO = URLRoot() & "db/" & [_DBID_RISK_ASSESSMENT_MATRIX_2] & "?a=API_AddRecord&_fid_77=" & URLEncode([Model ID#]) & "&apptoken=" & Token;

// Create the URL to redirect to the edit form of the newly created Risk Assessment Matrix record with additional parameters
var text URLTOEDIT = URLRoot() & "db/" & [_DBID_RISK_ASSESSMENT_MATRIX_2] & "?a=er&r=" & "c5" & "&rl=emd&rid=" & URLEncode("rid");

// Chain URLs: First create a Stakeholders record, then create a Risk Assessment Matrix record, then redirect to edit that new record
$URLONE & "&rdr=" & URLEncode($URLTWO & "&rdr=" & URLEncode(URLTOEDIT))
