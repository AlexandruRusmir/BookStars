<script>
// @ts-nocheck
    import { jwt_token } from "../store";

    export let bookId;

    let reviewText = '';
    let isPublic = true;
    let rating = 0;

    let jwtToken;
    jwt_token.subscribe(jwt => jwtToken = jwt);

    const submitReviewRequest = async () => {
        let responseData;
        await fetch(`http://127.0.0.1:5000/add_review/${bookId}`, {
            method: 'POST',
            mode: 'cors',
            cache: 'no-cache',
            headers: {
                'authorization-token': jwtToken,
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                isPublic: isPublic,
                text: reviewText,
                rating: rating
            })
        }).then((response) => response.json())
        .then((data) => {
            responseData = data;
        }).catch((error) => {
            console.error('Error:', error);
        });

        console.log(responseData);
    }

    const changeReviewRating = (e) => {
        rating = e.target.value;
    }
</script>

<body>
    <!-- {#if jwtToken !== ''} astea sunt comentate sa poti lucra tu aici. in mod normal, daca user-ul nu e logat, nu il lasam sa dea review-->
    <div class="add-review-box mx-5 p-3">
        <div>
            <div class="starrating risingstar d-flex justify-content-center flex-row-reverse">
                <input type="radio" id="star5" name="rating" value="5" on:click={changeReviewRating}/><label for="star5" title="5 star"></label>
                <input type="radio" id="star4" name="rating" value="4" on:click={changeReviewRating}/><label for="star4" title="4 star"></label>
                <input type="radio" id="star3" name="rating" value="3" on:click={changeReviewRating}/><label for="star3" title="3 star"></label>
                <input type="radio" id="star2" name="rating" value="2" on:click={changeReviewRating}/><label for="star2" title="2 star"></label>
                <input type="radio" id="star1" name="rating" value="1" on:click={changeReviewRating}/><label for="star1" title="1 star"></label>
            </div>
        </div>	
        <div class="my-3">
            <label for="make-review-public">Make review public</label>
            <input 
                id='make-review-public'
                type=checkbox 
                checked={isPublic} 
                on:click={() => {
                    isPublic = !isPublic;                    
                }}
            >
        </div>
        <div class="w-100">
            <input class="mx-5 review-input-style" placeholder="Write your review comment" on:input={e => {reviewText = e.target.value}}>
        </div>

        <div class="my-3">
            <button on:click={submitReviewRequest}>Submit Review</button>
        </div>
    </div>
    <!-- {/if} -->
</body>

<style>
    @import url(//netdna.bootstrapcdn.com/font-awesome/3.2.1/css/font-awesome.css);

    .starrating > input {display: none;}  /* Remove radio buttons */

    .starrating > label:before { 
    content: "\f005"; /* Star */
    margin: 2px;
    font-size: 8em;
    font-family: FontAwesome;
    display: inline-block; 
    }

    .starrating > label
    {
    color: #222222; /* Start color when not clicked */
    }

    .starrating > input:checked ~ label
    { color: #ffca08 ; } /* Set yellow color when star checked */

    .starrating > input:hover ~ label
    { color: #ffca08 ;  } /* Set yellow color when star hover */

    .add-review-box {
        font-family: Bitter;
        background-color: none;
    }

    .review-input-style {
        width: 90%;
    }
</style>