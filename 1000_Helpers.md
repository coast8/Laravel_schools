# 1 - 
		/app/Helpers/functions.php

		public static function sample(){
			return "Test Helpers OK";
		} 

		Helpers::sample($var);

# 2 - 
	"autoload": {
	    "classmap": [
	        "database/seeds",
	        "database/factories"
	    ],
	    "psr-4": {
	        "App\\": "app/"
	    },
	    "files": [
	        "app/Helpers/functions.php"
	    ]
	},


## Autoload
		composer dump-autoload

## tutorial ok
## https://www.youtube.com/watch?v=qOrseOC8TCE


## https://blog.especializati.com.br/criar-helpers-no-laravel/