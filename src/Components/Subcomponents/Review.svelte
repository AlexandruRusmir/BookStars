<script>
    export let imageUrl;
    export let review;
</script>

<body>
    <div>
        <div class="//rectangle-46"></div>
        <div class="//rectangle-46-1"></div>
        <div class="//book1">
          <img
            class="//book-1"
            src={imageUrl}
            alt="Book 1"
          />
        </div>
        <p class="//the-lorem-ipsum-gets //valign-text-middle //poppins-extra-light-black-20px">
          {review.text}
        </p>
        <p>
            {review.rating}
        </p>
        <div class="//rectangle-4627"></div>
        <div class="//rectangle-4633"></div>
        <div class="//rectangle-4674"></div>
        <div class="//rectangle-4675"></div>
        <button class="//btn">
          <img
          class="//like-10"
          src="\src\img\like-10@2x.png"
          alt="like 10"
        /></button>
        <button class="btn"> <img
          class="//like-15"
          src="\src\img\like-15-1@2x.png"
          alt="like 15"
        /></button>
      </div>
</body>

<style>
    @import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,600italic,600|Playfair+Display:700");
    
    .reviews-page {
      align-items: flex-end;
      background-color: var(--white);
      border: 1px none;
      display: flex;
      flex-direction: column;
      height: 2609px;
      overflow: hidden;
      width: 100%;
    }
    
    .flex-row-1 {
      align-items: center;
      display: flex;
      gap: 170px;
      height: 1745px;
      margin-top: 123px;
      min-width: 1185px;
    }
    
    
    .overlap-group-container {
      align-items: center;
      display: flex;
      flex-direction: column;
      min-height: 1745px;
      width: 1004px;
    }
    
    .overlap-group2 {
      height: 515px;
      margin-left: 6px;
      margin-top: 98px;
      position: relative;
      width: 998px;
    }
    
    .rectangle-4682 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 349px;
      position: absolute;
      top: 419px;
      width: 122px;
    }
    
    .rectangle-4685 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 527px;
      position: absolute;
      top: 419px;
      width: 122px;
    }
    
    .like-19 {
      height: 36px;
      left: 392px;
      object-fit: cover;
      position: absolute;
      top: 429px;
      width: 36px;
    }
    
    
    .rectangle-46-1 {
      background-color: var(--white);
      border: 1px solid;
      border-color: var(--silver-chalice);
      border-radius: 35px;
      box-shadow: 10px 8px 4px 
    #00000040;
      height: 70px;
      left: 26px;
      position: absolute;
      top: 0;
      width: 211px;
    }
    
    .overlap-group {
      height: 189px;
      margin-bottom: -8.77px;
      position: relative;
      width: 143px;
    }
    
    .book1 {
      align-items: flex-end;
      display: flex;
      height: 179px;
      justify-content: flex-end;
      left: 452px;
      min-width: 131px;
      position: absolute;
      top: 70px;
      transform: rotate(0.48deg);
    }
    
    .book-1 {
      height: 188px;
      margin-bottom: -8.34px;
      object-fit: cover;
      transform: rotate(-0.48deg);
      width: 140px;
    }
    
    .book2 {
      align-items: flex-end;
      display: flex;
      height: 179px;
      justify-content: flex-end;
      left: 446px;
      min-width: 133px;
      position: absolute;
      top: 85px;
      transform: rotate(0.39deg);
    }
    
    
    
    .book-2 {
      height: 188px;
      left: 1px;
      object-fit: cover;
      position: absolute;
      top: 0;
      transform: rotate(-0.39deg);
      width: 142px;
    }
    .book3 {
        align-items: flex-end;
      display: flex;
      height: 179px;
      justify-content: flex-end;
      left: 446px;
      min-width: 133px;
      position: absolute;
      top: 85px;
      transform: rotate(0.39deg);
    }
    .book-3 {
        height: 188px;
      margin-bottom: -8.34px;
      object-fit: cover;
      transform: rotate(-0.48deg);
      width: 140px;
    }
    
    .rectangle-4650 {
      background-color: 
    #8d8d8d;
      border-radius: 28px;
      height: 141px;
      left: 5px;
      position: absolute;
      top: 38px;
      width: 109px;
    }
    
    .rectangle-4683 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 349px;
      position: absolute;
      top: 419px;
      width: 122px;
    }
    
    .rectangle-46 {
      background: linear-gradient(180deg, rgb(222.06, 222.06, 222.06) 0.81%, rgb(249.69, 249.69, 249.69) 100%);
      border: 1px solid;
      border-color: var(--alto);
      border-radius: 49px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 473px;
      left: 0;
      position: absolute;
      top: 42px;
      width: 998px;
    }
    
    .like-18 {
      height: 35px;
      left: 572px;
      object-fit: cover;
      position: absolute;
      top: 431px;
      width: 35px;
    }
    
    .rectangle-4684 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 527px;
      position: absolute;
      top: 419px;
      width: 122px;
    }
    
    .overlap-group1 {
      height: 515px;
      margin-right: 6px;
      position: relative;
      width: 998px;
    }
    
    .rectangle-4674 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 524px;
      position: absolute;
      top: 422px;
      width: 122px;
    }
    
    
    .rectangle-4675 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 524px;
      position: absolute;
      top: 422px;
      width: 122px;
    }
    
    .lioness-m {
      height: 32px;
      left: 36px;
      letter-spacing: 1.43px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 22px;
      width: 196px;
    }
    .valign-text-middle {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    
    .rectangle-4627 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 346px;
      position: absolute;
      top: 422px;
      width: 122px;
    }
    
    .like-15 {
      height: 36px;
      left: 389px;
      object-fit: cover;
      position: absolute;
      top: 432px;
      width: 36px;
    }
    
    .rectangle-4633 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 346px;
      position: absolute;
      top: 422px;
      width: 122px;
    }
    
    .like-10 {
      height: 35px;
      left: 569px;
      object-fit: cover;
      position: absolute;
      top: 434px;
      width: 35px;
    }
    
    .the-lorem-ipsum-gets {
      height: 93px;
      left: 188px;
      letter-spacing: 1.3px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 276px;
      width: 672px;
    }
    
    .the-lorem-ipsum-gets-1 {
      height: 160px;
      left: 158px;
      letter-spacing: 1.3px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 249px;
      width: 716px;
    }
    
    .overlap-group3 {
      height: 515px;
      margin-right: 6px;
      margin-top: 102px;
      position: relative;
      width: 998px;
    }
    
    .rectangle-4679 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 355px;
      position: absolute;
      top: 417px;
      width: 122px;
    }
    
    .rectangle-4681 {
      background-color: var(--fantasy);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 533px;
      position: absolute;
      top: 417px;
      width: 122px;
    }
    
    .like-17 {
      height: 36px;
      left: 398px;
      object-fit: cover;
      position: absolute;
      top: 427px;
      width: 36px;
    }
    
    .name-1 {
      height: 32px;
      left: 36px;
      letter-spacing: 1.43px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 22px;
      width: 196px;
    }
    
    .name {
      height: 32px;
      left: 36px;
      letter-spacing: 1.43px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 22px;
      width: 196px;
    }
    
    .like-16 {
      height: 35px;
      left: 578px;
      object-fit: cover;
      position: absolute;
      top: 429px;
      width: 35px;
    }
    
    .rectangle-4680 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 533px;
      position: absolute;
      top: 417px;
      width: 122px;
    }
    
    .book2 {
      align-items: flex-end;
      display: flex;
      height: 178px;
      left: 443px;
      min-width: 135px;
      position: absolute;
      top: 73px;
      transform: rotate(-0.41deg);
    }
    
    .book-2 {
        height: 188px;
      margin-bottom: -8.34px;
      object-fit: cover;
      transform: rotate(-0.48deg);
      width: 140px;
    }
    
    .rectangle-4678 {
      background-color: var(--romance);
      border-radius: 36px;
      box-shadow: 0px 4px 4px 
    #00000040;
      height: 55px;
      left: 355px;
      position: absolute;
      top: 417px;
      width: 122px;
    }
    
    .the-lorem-ipsum-gets-2 {
      height: 123px;
      left: 54px;
      letter-spacing: 1.3px;
      line-height: normal;
      position: absolute;
      text-align: center;
      top: 271px;
      width: 913px;
    }
    
    .overlap-group5 {
      align-items: flex-start;
      background-color: rgb(243, 228, 160);
      display: flex;
      height: 111px;
      width:100%;
      margin-top: 50px;
      padding: 38.6px 85.4px;
    }
    
    .discover-our-users-reviews {
      height: 30px;
      width: 559px;
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
    .poppins-extra-light-black-20px {
      color: var(--black);
      font-family: var(--font-family-poppins);
      font-size: var(--font-size-s);
      font-weight: 200;
      font-style: normal;
    }
    
    
    </style>