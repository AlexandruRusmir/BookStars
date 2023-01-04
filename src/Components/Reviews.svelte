<script>
    import Review from "./Subcomponents/Review.svelte";

    export let imageUrl;
    export let reviews;
</script>

<body>
    <div>
        <div>
          <div>
            {#each reviews as review}
              <Review 
                review={review}
                imageUrl={imageUrl}
              />
            {/each}
          </div>
      </div>
</body>

<style>
@import url("https://fonts.googleapis.com/css?family=Poppins:200,400,600|Bitter:400,600italic,600|Playfair+Display:700");


</style>
