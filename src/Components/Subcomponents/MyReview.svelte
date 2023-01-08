<script>
    export let myReview;

    import { jwt_token } from "../../store";
    import { bookMockData, reviewsMockData } from "../../mockData/mockData";

    let jwtToken;
    jwt_token.subscribe((jwt) => (jwtToken = jwt));

    const getBookData = async () => {
        let responseData = {
            bookData: bookMockData,
            reviews: reviewsMockData,
        };
        await fetch(`http://127.0.0.1:5000/book/${myReview.bookId}`, {
            mode: "cors",
            headers: {
                "authorization-token": jwtToken,
                "Content-Type": "application/json",
            },
        })
            .then((response) => response.json())
            .then((data) => {
                if (data.message != "a valid token is missing") {
                    responseData = data;
                }
            })
            .catch((error) => {
                console.error("Error:", error);
            });

        return responseData;
    };
</script>

<body>
    <div class="col-sm-6">
    {#await getBookData() then data}
        <div class="card">
            <div class="row">
                <div class="col-md-4">
                    <img
                        class="img-fluid"
                        src={data.bookData.imageUrl}
                        alt="Book 1"
                        height="200px"
                    />
                </div>
                <div class="col-md-8">
                    <p class="card-title">"{data.bookData.name}"</p>
                    <p>
                        My message: {myReview.text}
                    </p>
                    <p>
                        Rating: {myReview.rating}
                    </p>
                    <p>
                        My Review score: {myReview.score}
                    </p>
                </div>
            </div>
        </div>
    {/await}
</div>
</body>

<style>
    body{
        font-family: Bitter;
    }
    .card {
        margin: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        max-height: 100%;
        width: 50%;
        margin-bottom: 3rem;
        border-radius: 1.5rem;
        padding: 2rem;
        --bg-opacity: 1;
        background-color: rgba(255, 255, 255, var(--bg-opacity));
        box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.46), 0 1px 2px 0 rgb(0 0 0 / 6%);
        box-sizing: border-box;
        border: 0 solid;
    }
    .card-title {
        font-size: larger;
        font-style: italic;
        font-weight: bold;
    }
    img {
        border-radius: 5px;
        height: auto;
    }
    p{
        margin-top: 15px;
    }
</style>

