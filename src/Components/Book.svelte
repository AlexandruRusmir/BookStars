<script>
</script>

<body>
    <div class="book-page" id="book-page">
        <div class="overlap-group5">
            <h1 class="book-title">'Book Title'</h1>
            <!-- <div
                class="the-adventures-of-tom-sawyer"
                src="\src\img\-the-adventures-of-tom-sawyer-@1x.jpg"
                alt="The Adventures of Tom Sawyer"
            > -->
                <div class="book-details">
                    <!-- svelte-ignore a11y-img-redundant-alt -->
                    <img
                        class="book-picture"
                        src="\src\img\book4.png"
                        alt="Picture of Book"
                    />
                </div>
                <img
                    class="rating"
                    src="\src\img\rating-1@2x.png"
                    alt="Rating"
                />
                <p
                    class="pub-date-1876-page valign-text-middle bitter-light-black-20px"
                >
                    <span
                        ><span class="bitter-light-black-20px"
                            >Pub Date:
                        </span><span class="bitter-normal-black-20px"
                            >1876&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span
                        ><span class="bitter-light-black-20px">Page Count:</span
                        ><span class="bitter-normal-black-20px">
                            272&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span
                        ><span class="bitter-light-black-20px">Publisher:</span
                        ><span class="bitter-normal-black-20px">
                            Penguin Classics</span
                        >
                    </span>
                </p>
                <p class="description valign-text-middle bitter-normal-black-20px">
                    "The Adventures of Tom Sawyer," written in 1876, is one of the best-loved and most quoted works of American author Mark Twain (whose real
                    name was Samuel Langhorne Clemens). The novel, which sold slowly at first for the author, can be appreciated on multiple levels. Children
                    can enjoy the adventure story, and adults can appreciate the satire.
                  </p>
            </div>
        </div>
    <!-- </div> -->
</body>

<style>
    @import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,600italic,600|Playfair+Display:700");
    @import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,600italic,300,500,400italic,600|Playfair+Display:700");

.description {
  align-self: center;
  height: 224px;
  letter-spacing: 1.7px;
  line-height: 35px;
  margin-left: 108px;
  margin-top: 59px;
  text-align: center;
  width: 1083px;
}

.valign-text-middle {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
    .book-page {
        align-items: flex-end;
        background-color: var(--white);
        border: 1px none;
        display: flex;
        flex-direction: column;
        height: 2609px;
        overflow: hidden;
        width: 1365px;
    }

    .book-title{
    
        font-family: Bitter;
        font-size: 40px;
        font-weight: bolder;
    }

    .overlap-group5 {
        align-items: flex-start;
        background-color: rgb(243, 228, 160);
        /* display: flex; */
        height: 111px;
        margin-right: -3.97px;
        margin-top: 50px;
        min-width: 1373px;
        padding: 38.6px 85.4px;
        width:100%;
    }

    .the-adventures-of-tom-sawyer {
        height: 33px;
        margin-right: 83.03px;
        width: 553px;
    }

    .book-picture {
        height: 699px;
        margin: 100px 0 50px 300px;
        object-fit: cover;
        transform: rotate(-0.65deg);
        width: 513px;
    }

    .rating {
  height: 37px;
  margin-left: 450px;
  width: 210px;
}

    @import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,300,600italic,600|Playfair+Display:700");

    .pub-date-1876-page {
        height: 8px;
        letter-spacing: 1.3px;
        line-height: normal;
        margin-top: 46px;
        text-align: center;
        width: 1083px;
    }

    .valign-text-middle {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>
