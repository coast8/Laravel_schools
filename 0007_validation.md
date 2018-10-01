
## validation
	https://laravel.com/docs/5.7/validation

## tutorial
	use Illuminate\Support\Facades\Hash;
	use Validator;
    
    public function register(Request $request)
    {
        // validators
        $rules = [
            'firstName' => 'required',
            'email' => 'unique:users|required',
            'password' => 'required'
        ];
        $input = $request->only('firstName', 'email', 'password');
        
        // verifying that the validations
        // they are correct
        $validator = Validator::make($input, $rules);
        // error in validators.
        if($validator->fails()) {
            return response()->json(['success'=> false, 'error'=> $validator->messages()]);
        }
        $firstName = $request->firstName;
        $lastName = $request->lastName;
        $email = $request->email;
        $password = $request->password;
        // creating a new user.
        $user = User::create([
            'firstName' => $firstName,
            'lastName' => $lastName,
            'email' => $email,
            'password' => Hash::make($password)
        ]);
        
        return response()->json(['success' => true]);
    }
