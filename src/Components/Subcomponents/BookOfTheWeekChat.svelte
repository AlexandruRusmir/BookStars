<script>
// @ts-nocheck
    import { onMount } from "svelte";
    import { jwt_token } from "../../store";
    import { chatMessagesMockData } from "../../mockData/mockData";
    import ChatMessage from "./ChatMessage.svelte";

    let jwtToken;
    jwt_token.subscribe((jwt) => (jwtToken = jwt));

    let chatMessage = '';
    let messages = [];

    const getChat = async () => {
        let responseData = {chat: chatMessagesMockData};
        await fetch(`http://127.0.0.1:5000/chat`, {
            mode: 'cors',
            headers: {
                "authorization-token": jwtToken,
                "Content-Type": "application/json",
            },
        }).then((response) => response.json())
        .then((data) => {
            responseData = data;
        }).catch((error) => {
            console.error('Error:', error);
        });

        return responseData;
    };

    const sendMessage = async () => {
        if(!chatMessage) {
            return;
        }

        let responseData = {chat: chatMessagesMockData};
        await fetch(`http://127.0.0.1:5000/chat`, {
            method: 'POST',
            mode: 'cors',
            headers: {
                "authorization-token": jwtToken,
                "Content-Type": "application/json",
            },
            body: JSON.stringify({
                message: chatMessage
            }),
        }).then((response) => response.json())
        .then((data) => {
            responseData = data;
        }).catch((error) => {
            console.error('Error:', error);
        });

        return responseData;
    };

    onMount(async () => {
        const chatMessages = await getChat();
        messages = chatMessages.chat;
    })
</script>

<body>
    <div class="mx-5 mt-2">
        <input on:change={(e) => {chatMessage = e.target.value}}>
        <button on:click={sendMessage}>Send message</button>
    </div>
    <div>
        {#each messages as message}
            <ChatMessage
                userName={message.userName}
                message={message.message}
            />
        {/each}
    </div>
</body>

<style>

</style>