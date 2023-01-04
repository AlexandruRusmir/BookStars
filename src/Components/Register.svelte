<script>
    // @ts-nocheck
    import { jwt_token } from "../store";
    import { push } from 'svelte-spa-router';
    
    let name = '';
    let password = '';
    let confirmPassword = '';

    let passwordIsNotTheSameAsConfirmPassword = false;
    let registerError = false;
    
    const isPasswordNotTheSameAsConfirmPassword = () => {
        if (password === confirmPassword) {
            passwordIsNotTheSameAsConfirmPassword = false;
        }
        else {
            passwordIsNotTheSameAsConfirmPassword = true;
        }

        return passwordIsNotTheSameAsConfirmPassword;
    }

    const sendRegisterRequest = async () => {
        if (isPasswordNotTheSameAsConfirmPassword()) {
            return;
        }

        let responseData;
        await fetch(`http://127.0.0.1:5000/register`, {
            method: 'POST',
            mode: 'cors',
            body: JSON.stringify({
                name: name,
                password: password
            }),
            headers: {
                'Content-Type': 'application/json'
            },
        }).then((response) => response.json())
        .then((data) => {
            responseData = data;
        }).catch((error) => {
            console.error('Error:', error);
        });

        if (responseData.message === 'registered successfully') {
            let responseData;
            await fetch(`http://127.0.0.1:5000/login`, {
                method: 'POST',
                mode: 'cors',
                cache: 'no-cache',
                headers: {
                    'Authorization': ('Basic ' + btoa(name + ':' + password))
                }
            }).then((response) => response.json())
            .then((data) => {
                responseData = data;
            }).catch((error) => {
                console.error('Error:', error);
            });

            jwt_token.set(responseData.token ?? '');
            push('#/')
        }
    }
</script>

<body>
    <div class="mt-5 flex-column d-flex align-items-center justify-content-center">
        <p>
            Register
        </p>
        <div>
            <div class="my-2">
                <div>
                    <span>Username:</span>
                </div>
                <div>
                    <input placeholder="Enter your username" on:input={e => {name = e.target.value}}>
                </div>
            </div>
            <div class="my-2">
                <div>
                    <span>Password:</span>
                </div>
                <div>
                    <input type="password" placeholder="Enter your password" on:input={e => {password = e.target.value}}>
                </div>
            </div>
            <div class="my-2">
                <div>
                    <span>Confirm password: </span> 
                </div>
                <div>
                    <input type="password" placeholder="Confirm your password" on:input={e => {confirmPassword = e.target.value}}>
                </div>
            </div>
        </div>
        {#if passwordIsNotTheSameAsConfirmPassword}
            <p class="error-message">Password is not the same as the confirmed password!</p>
        {/if}
        {#if registerError}
            <p class="error-message">Error registering. Please check your username and password</p>
        {/if}
        <button class="mt-3" on:click={sendRegisterRequest}>Register</button>
        <a class="nav-link" href="#/login">Already have an account? </a>
    </div>
</body>

<style>
    .error-message {
        color: rgb(235, 42, 42);
    }
</style>