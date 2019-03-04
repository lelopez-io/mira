<template>
  <div class="about">
    <h1>About MIRA</h1>
    <h2>MIRA aims at bringing social features to movie streaming</h2>
    <p>
      Mira is the spanish word for look, as in look at what your friends are
      watching, have watched, or stopped watching while browsing through titles.
      This idea could be extended to include messages both public and private
      with the option to filter out possible spoilers.
    </p>

    <p>
      Mira was built using Vue.js and AWS Lambdas for a RESTful API. At the
      moment it fetches a list of movies from
      <a href="https://www.themoviedb.org" target="_blank">The Movie Database</a
      >. Once you click on a title, it's information will be displayed along
      with a new button next the the thumbs up/down. This number represents how
      many of your friends have interacted with this title. If you click on this
      'social button' a list of those friends will appear along with the percent
      watched in the form of a loading circle/border around their photo. As long
      as friends are willing to share this info, I believe it's a good measure
      for finding new titles.
    </p>
    <h3>Some Todos</h3>
    <ul>
      <li>
        The Lambda function can handle a specific genre to query but that
        functionality is not present on the front end just yet.
      </li>
      <li>
        X-Overflow is not correctly hidden in Safari at the moment. This has to
        do with the video container not having a fixed position. Since I want
        the featured video to scroll with the page this needs to be tinkered
        with. For now this website works best with Google Chrome.
      </li>
      <li>
        For the most part the UI is responsive. The one thing needed is to
        switch the flex orientation to column for title info when a title is
        clicked using a mobile browser.
      </li>
      <li>
        At the moment the social component is ready to accept dynamic data for
        username, profile photo, and percent watched. Given more time, I'd focus
        on setting up an api request or database to get this information.
      </li>
    </ul>
    <h3>Code</h3>
    <p>
      You can find all the code for both the Web App and the serverless
      functions here
    </p>
    <ul>
      <li>
        <a href="https://github.com/lelopez-io/mira" target="_blank"
          >https://github.com/lelopez-io/mira</a
        >
      </li>
      <li>
        <a href="https://github.com/lelopez-io/mira-sls" target="_blank"
          >https://github.com/lelopez-io/mira-sls</a
        >
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.about {
  padding: 30px;
  max-width: 650px;
  margin-left: auto;
  margin-right: auto;

  & h1 {
    margin-bottom: 0;
  }

  & h2 {
    margin-top: 0;
    color: #e50914;
  }
}
</style>
