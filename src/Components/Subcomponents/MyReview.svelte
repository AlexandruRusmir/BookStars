<script>
    export let myReview;

    import { jwt_token } from "../../store";
    import { bookMockData, reviewsMockData } from '../../mockData/mockData';

    let jwtToken;
    jwt_token.subscribe(jwt => jwtToken = jwt);
    
    const getBookData = async () => {
        let responseData = {
            bookData: bookMockData,
            reviews: reviewsMockData
        };
        await fetch(`http://127.0.0.1:5000/book/${myReview.bookId}`, {
            mode: 'cors',
            headers: {
                'authorization-token': jwtToken,
                'Content-Type': 'application/json'
            },
        }).then((response) => response.json())
        .then((data) => {
            if (data.message != 'a valid token is missing') {
                responseData = data;
            }
        }).catch((error) => {
            console.error('Error:', error);
        });

        return responseData;
    }
</script>

<body>
    {#await getBookData() then data}
        <div class="my-review-box">
            <div class="//rectangle-46"></div>
            <div class="//rectangle-46-1"></div>
            <div class="//book1">
            <img
                class="//book-1"
                src={data.bookData.imageUrl}
                alt="Book 1"
                height="200px"
            />
            <p>{data.bookData.name}</p>
            </div>
            <p class="//the-lorem-ipsum-gets //valign-text-middle //poppins-extra-light-black-20px">
                My message: {myReview.text}
            </p>
            <p>
                Rating: {myReview.rating}
            </p>
            <p>
                My Review score: {myReview.score}
            </p>
        </div>
    {/await}
</body>

<style>
    .my-review-box {
        background-color: #dedede;
        border-radius: 8px;
    }
</style>