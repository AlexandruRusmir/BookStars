<script>
  // @ts-nocheck
  import { jwt_token } from "../../store";
  export let imageUrl;
  export let review;

  let jwtToken;
  jwt_token.subscribe((jwt) => (jwtToken = jwt));

  const appreciateReviewRequest = async (likeOrNot) => {
    let responseData;
    await fetch(`http://127.0.0.1:5000/appreciate_review/${review.id}`, {
      method: "POST",
      mode: "cors",
      cache: "no-cache",
      headers: {
        "authorization-token": jwtToken,
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        like: likeOrNot,
      }),
    })
      .then((response) => response.json())
      .then((data) => {
        responseData = data;
      })
      .catch((error) => {
        console.error("Error:", error);
      });
  };

</script>

<body>
  <div class="card">
    <div class="row">
      <div class="col-md-4">
        <img class="img-fluid rounded-start" src={imageUrl} alt="Book 1" />
      </div>
      <div class="col-md-8">
        <p class="text-review">
          {review.text}
        </p>
        <p>
          {review.rating}
        </p>
      </div>
      <div class="like-dislike">
    <button class="btn" id="green" on:click={appreciateReviewRequest(true)}>
      <i class="fa fa-thumbs-up fa-lg" aria-hidden="true" />
      </button>
    <button class="btn" id="red" on:click={appreciateReviewRequest(false)}>
      <i class="fa fa-thumbs-down fa-lg" aria-hidden="true" />
    </button>
  </div>
  </div>

</body>


<style>
  @import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,600italic,600|Playfair+Display:700");

  .card {
    max-height: 100%;
    width: 800px;
    margin-bottom: 3rem;
    border-radius: 1.5rem;
    padding: 2rem;
    --bg-opacity: 1;
    background-color: #fff;
    background-color: rgba(255, 255, 255, var(--bg-opacity));
    box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.46), 0 1px 2px 0 rgb(0 0 0 / 6%);
    box-sizing: border-box;
    border: 0 solid;
  }

  img {
    /* align-items: center;
    margin: 20px;
    padding: 20px;  */
    height: 200px;
    /* width: 20%;
    text-align: center; */
  }
.like-dislike{
  text-align: center;
}
  button {
    cursor: pointer;
    outline: 0;
    outline-color: rgb(3, 3, 3);
  }

  .btn:focus {
    outline: none;
  }

  #green:hover {
    color: green;
  }

  #red:hover{
    color: red;
  }
  .text-review {
    margin-top: 20px;
  }



  /* Variables */

  :root {
    --black: rgba(0, 0, 0, 1);
    --white: rgba(255, 255, 255, 1);

    --font-size-s: 20px;
    --font-size-m: 26px;

    --font-family-bitter: "Bitter";
    --font-family-poppins: "Poppins";
  }

</style>