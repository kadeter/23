$response = Request::get('https://instagram.com/kevin');
$pageString = $response->body();
$arr = explode('window._sharedData = ', $pageString);
$json = explode(';</script>', $arr[1]);
$userArray = json_decode($json[0], true);
$userData = $userArray['entry_data']['ProfilePage'][0]['user'];
echo $userData['username']; // Теперь можно делать вот так
echo $userData['follows']['count'] // или вот так
echo $userData['is_private']; // ну вы поняли
