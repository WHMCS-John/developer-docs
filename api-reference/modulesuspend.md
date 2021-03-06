+++
title = "ModuleSuspend"
toc = true
+++

Runs the module suspend action for a given service.

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "ModuleSuspend" | Required |
| accountid | int | The service ID to run the action for | Required |
| suspendreason | string | A reason for the suspension | Optional |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'ModuleSuspend',
            'username' => 'ADMIN_USERNAME',
            'password' => 'ADMIN_PASSWORD',
            'accountid' => '1',
            'suspendreason' => 'Abuse',
            'responsetype' => 'json',
        )
    )
);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'ModuleSuspend';
$postData = array(
    'accountid' => '1',
    'suspendreason' => 'Abuse',
);
$adminUsername = 'ADMIN_USERNAME';

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success"
}
```


### Error Responses

Possible error condition responses include:

* Server response message


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |
