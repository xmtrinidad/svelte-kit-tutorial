<script>
  // Testing object mutation and page renders
  let objPageTitle = {
    wordOne: 'Test',
    wordTwo: {
      letters: ['t', 'h', 'i', 'n', 'g'],
      isThing: true,
      whatEvenIs: { what: 'Bruh'}
    }
  }

  const updateWordOne = () => {
    objPageTitle.wordOne =  "TESTTTTTING";
  };

  const updateWordTwo = () => {
    objPageTitle.wordTwo.letters[2] = 'X';
    // objPageTitle.wordOne =  "TESTTTTTING";
  };
</script>

<div class="index">
  <nav>
    <a href="/about">About</a>
    <a href="/guides">Guides</a>
  </nav>
  <h2>{objPageTitle.wordOne} {objPageTitle.wordTwo.letters.join('')}</h2>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Similique, explicabo dignissimos distinctio voluptatibus quo nulla est sapiente excepturi. Fuga hic quasi ullam, qui cumque laboriosam. Culpa mollitia harum hic. Repudiandae quam voluptatum praesentium, ea illo, fugiat cum minus nulla perferendis sequi similique esse doloribus maxime odit harum earum vitae error!</p>

  <button on:click={updateWordOne}>Update Word One</button>
  <button on:click={updateWordTwo}>Update Word two</button>
  <div class="input-container">
    <label for="two-way-bind">BIIIIIIIIIIIIIIIIIIIIIND</label>
    <input type="text" id="two-way-bind" bind:value={objPageTitle.wordOne}>
  </div>
  
</div>

<style></style>



