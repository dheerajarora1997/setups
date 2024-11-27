# setups
# for compile sass to  css in min - sass --style=compressed scss:css
#Homestead vagrant index file
{"version":1,"machines":{"95c6d42e096b4ac7ae9b8a953e2d3ddf":{"local_data_path":"E:/code/Homestead/.vagrant","name":"homestead","provider":"virtualbox","state":"saved","vagrantfile_name":null,"vagrantfile_path":"E:/code/Homestead","updated_at":null,"extra_data":{"box":{"name":"laravel/homestead","provider":"virtualbox","version":"8.1.0"}}}}}





#Setting up .env file in wordpress

composer init

composer require  vlucas/phpdotenv


Place code in wp-config

require_once(__DIR__ . '/vendor/autoload.php');
$dotenv = Dotenv\Dotenv::createImmutable(__DIR__);
$dotenv->load();


composer dump-autoload -o

#code in.env file

# Email config video
https://www.youtube.com/watch?v=nNGcvz1Sc_8

# Example Of Local Environment File
APP_ENV=local

DB_NAME=smart-led
DB_USER=root
DB_PASSWORD=
DB_HOST=localhost
DB_PREFIX=wp_
DB_DEBUG=true

GOOGLE_ANALYTICS_ENABLE=false
GOOGLE_ANALYTICS_KEY=UA-xxx


#code for wp-config

// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', getenv('DB_NAME'));

/** MySQL database username */
define('DB_USER', getenv('DB_USER'));

/** MySQL database password */
define('DB_PASSWORD', getenv('DB_PASSWORD'));

/** MySQL hostname */
define('DB_HOST', getenv('DB_HOST'));

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8mb4');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');

/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies. This will force all users to have to log in again.
 *
 * @since 2.6.0
 */
define('AUTH_KEY', 'dBxCXjL_UDGG^1C_MV03^5drUvx2+oX?[/;J)l#8fI-aR9;i%7gMtcUq +-s:|ma');
define('SECURE_AUTH_KEY', 'rOg.[])<J&7Dd&$|7Z[ 9c5+0)88mtB}.nDriN;-(-ZQ$8Q:Au_%Rz y#wD#@WFe');
define('LOGGED_IN_KEY', 'Y}NXe.<qBjiJ)qWoYuZ#;q}|].EszDx5NmTbK0QbeG[HI|[eEo$/3N[2)=y#z~c>');
define('NONCE_KEY', '-JIW|Nj3yi7;GV_&-g4O#?bR1B/Wt#{^Qgz&N+L%eICB,&oK~.pd8]00!th)IF]^');
define('AUTH_SALT', '>tcV6wvTN.MV8z0S:4tH;(}U>PH}ij|III7xY/Hd.IaA#T}x*cPhvBXaY|hlBE:M');
define('SECURE_AUTH_SALT', 'q6nf0iH&(LbYf!!5NT@fU[Eocd,cqgejUio]}SOeWAIh?WG$YIYjq9?^6Og83_xI');
define('LOGGED_IN_SALT', '7Gh^~F9XeABK~*nm5zhq0+rfQC9Y7CbE<Y@L)|JW:b~`[:V9ER^Tn?S)v7:}|C3+');
define('NONCE_SALT', 'u#wbIL{b7aSPb*Dat&*m5|~d<}SW7B V0 XTt5P*+Y]2Rn:Zb/LmNuI<x0pY:qY@');







