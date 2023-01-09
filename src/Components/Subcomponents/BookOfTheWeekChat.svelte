<script>
    import { jwt_token } from "../../store";
    import { chatMessagesMockData } from "../../mockData/mockData";
    import ChatMessage from "./ChatMessage.svelte";

    let jwtToken;
    jwt_token.subscribe((jwt) => (jwtToken = jwt));

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
</script>

<body>
    <div>
        
    </div>
    <div>
        {#await getChat() then data}
            {#each data.chat as chatMessage}
                <ChatMessage
                    userName={chatMessage.userName}
                    message={chatMessage.message}
                />
            {/each}
        {/await}
    </div>
</body>

<style>

</style>