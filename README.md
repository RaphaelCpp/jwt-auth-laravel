Jwt Auth :

first :

composer require tymon/jwt-auth 👍

second :

paste : Tymon\JWTAuth\Providers\LaravelServiceProvider::class in 'providers' (config/app.php)
paste : 'JWTAuth' => Tymon\JWTAuth\Facades\JWTAuth::class, + 'JWTFactory' => Tymon\JWTAuth\Facades\JWTFactory::class, (config/app.php)

third :

php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"

four :

php artisan jwt:secret

five :

add class User extends Authenticatable implements JWTSubject in app model

six :

add :
'api' => [
'driver' => 'jwt',
'provider' => 'users',
'hash' => false,
],

after guards in (config/auth.php)
