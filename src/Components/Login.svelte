<script>
// @ts-nocheck
    import { jwt_token } from "../store";
    import { push } from 'svelte-spa-router';

    let name = '';
    let password = '';
    let loginError = false;
    
    const sendLoginRequest = async () => {
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
</script>

<body>
    <div class="mt-5 flex-column d-flex align-items-center justify-content-center">
        <p>
            Login
        </p>
        <div>
            <div class="my-2">
                <div>
                    <span>Username: </span>
                </div>
                <div>
                    <input placeholder="Enter your username" on:input={e => {name = e.target.value}}>
                </div>
            </div>
            <div class="my-2">
                <div>
                    <span>Password:&nbsp; </span> 
                </div>
                <div>
                    <input type="password" placeholder="Enter your password" on:input={e => {password = e.target.value}}>
                </div>
            </div>
        </div>
        {#if loginError}
            <p class="error-message">Error logging in. Please check your username and password</p>
        {/if}
        <button class="mt-3" on:click={sendLoginRequest}>Login</button>
         <a class="nav-link" href="#/register">Don't have an account?</a>
    </div>
</body>

<style>
    .error-message {
        color: rgb(235, 42, 42);
    }
</style>