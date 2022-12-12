<script>
    import BookCard from "./Subcomponents/BookCard.svelte";
</script>

<!--<BookCard bookId={2} title={"In jurul lumii in 3 zile"} author={"Gigel"} /> -->
<body>
    <div id="large-th">
        <div class="container">
            <div id="list-th">
                <a style="color:black;" href="#/book_details/:id">
                <div class="book">
                    <div class="cover">
                        <img
                            src="https://s-media-cache-ak0.pinimg.com/564x/f9/8e/2d/f98e2d661445620266c0855d418aab71.jpg" alt='Book 1'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Frankenstein<br />
                            <span class="author">Mary Shelley</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="https://alysbcohen.files.wordpress.com/2015/01/little-princess-book-cover.jpg" alt='Book 2'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            A Little Princess<br />
                            <span class="author">Frances Hodgson Burnett</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://www.publishersweekly.com/images/data/ARTICLE_PHOTO/photo/000/028/28129-1.JPG" alt='Book 3'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Roughing It<br />
                            <span class="author">Mark Twain</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://talkingwriting.com//sites/default/files/Bird-by-Bird-image1.jpg" alt='Book 4'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Bird By Bird<br />
                            <span class="author">Anne Lamott</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://d.gr-assets.com/books/1414348859l/23209971.jpg" alt='Book 5'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Girl at War<br />
                            <span class="author">Sara Novic</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://prodimage.images-bn.com/pimages/9780062315007_p0_v2_s192x300.jpg" alt='Book 6'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            The Alchemist<br />
                            <span class="author">Paulo Coelho</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://eastchapelhillobserver.com/wp-content/uploads/2015/02/amazondotcom.jpg" alt='Book 7'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Anne of Green Gables<br />
                            <span class="author">Lucy Maud Montgomery</span>
                        </p>
                    </div>
                </div>
            </a>
            <a style="color:black;" href="#/book_details/:id" >
                <div class="book">
                    <div class="cover">
                        <img
                            src="http://www.penguinbooksindia.com/sites/default/files/book_image/9780143416319.jpg" alt='Book 8'
                        />
                    </div>
                    <div class="description">
                        <p class="title">
                            Animal Farm<br />
                            <span class="author">George Orwell</span>
                        </p>
                    </div>
                </div>
            </a>
            </div>
        </div>
    </div>
</body>

<style>
    .container {
        margin: 0 auto;
        max-width: 910px;
    }

    .book {
        transition:transform 0.25s ease;
        display: inline-block;
        width: 230px;
        height: 390px;
        box-shadow: 0 0 20px #aaa;
        margin: 25px;
        padding: 10px 10px 0 10px;
        vertical-align: top;
        transition: height 1s;
    }
    /* star button */
    .book:after {
        font-family: FontAwesome;
        content: "\f006";
        font-size: 35px;
        position: relative;
        left: -0.1cm;
        top: -0.8cm;
        float: right;
    }
    .book:hover{
    -webkit-transform:scale(0.5); 
    transform:scale(1.1);
}

    .cover {
        border: 2px solid gray;
        height: 80%;
        overflow: hidden;
    }

    .cover img {
        width: 100%;
    }

    .book p {
        margin-top: 12px;
        font-size: 20px;
    }

    .book .author {
        font-size: 15px;
    }
    @media (max-width: 941px) {
        .container {
            max-width: 700px;
        }
        .book {
            margin: 49px;
        }
    }
    @media (max-width: 730px) {
        .book {
            display: block;
            margin: 0 auto;
            margin-top: 50px;
        }
    }

</style>
