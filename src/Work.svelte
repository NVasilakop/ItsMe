<script>
    let pageName = "Work";
</script>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }

    ul.experiences {
        padding-left: 15px;
        margin-top: -1px;
    }
    ul.experiences li {
        padding-left: 33px;
        margin-bottom: 2.5em;
        list-style: none;
        background: url("../img/misc/list-bullet-darkgray.png") no-repeat;
    }
    ul.experiences li.green {
        background: url("../img/misc/list-bullet-green.png") no-repeat;
    }
    ul.experiences li.blue {
        background: url("../img/misc/list-bullet-blue.png") no-repeat;
    }
    ul.experiences li.pink {
        background: url("../img/misc/list-bullet-pink.png") no-repeat;
    }
    .where {
        font-size: 1.2857em; /* 18/16 -> 18px */
        font-weight: 300;
        display: inline;
        margin-right: 0.5em;
    }
    .what {
        font-size: 0.75em; /* 12/16 -> 12px */
        font-weight: 700;
        text-transform: uppercase;
        color: #fff;
        background-color: #444444;
        display: inline-block;
        padding: 0 12px;
        margin: -5px 0.5em 0 0 !important;
        -webkit-border-radius: 3px;
        -moz-border-radius: 3px;
        border-radius: 3px;
    }
    .what.green {
        background-color: #c4df9b;
    }
    .what.blue {
        background-color: #6dcff6;
    }
    .what.pink {
        background-color: #f06eaa;
    }
    .when {
        float: right;
        color: #b9b9b9;
        font-style: italic;
    }
    .description {
        display: block;
        margin-top: 0.5em;
    }

    /* BORDERS AND BULLETS */

    p {
        /*CSS reset*/
        margin-bottom: 0;
    }

    ul.work li {
        position: relative; /* so that pseudoelements are positioned relatively to their "li"s*/
        /* use padding-bottom instead of margin-bottom.*/
        margin-bottom: 0; /* This overrides previously specified margin-bottom */
        padding-bottom: 2.5em;
    }

    ul.work li:after {
        /* bullets */
        content: url("http://upload.wikimedia.org/wikipedia/commons/thumb/3/30/RedDisc.svg/20px-RedDisc.svg.png");
        position: absolute;
        left: -26px; /*adjust manually*/
        top: 0px;
    }

    ul.work li:before {
        /* lines */
        content: "";
        position: absolute;
        left: -16px; /* adjust manually */
        border-left: 1px solid black;
        height: 100%;
        width: 1px;
    }

    ul.work li:first-child:before {
        /* first li's line */
        top: 6px; /* moves the line down so that it disappears under the bullet. Adjust manually */
    }

    ul.work li:last-child:before {
        /* last li's line */
        height: 6px; /* shorten the line so it goes only up to the bullet. Is equal to first-child:before's top */
    }
</style>

<main>
    <h1>{pageName}</h1>
    <ul class="work">
        <!-- Experience -->
        <li class="green">
            <div class="where">
                Mathematics & Applied Mathematics Department of Crete
            </div>
            <h3 class="what green">Teaching Assistant</h3>
            <div class="when">January 2013 - January 2014</div>
            <p class="description">Teaching Assistant in:</p>
            <p>Physics I</p>
            <p>Mathematical Modeling</p>
        </li>
        <li class="green">
            <div class="where">National Bank Of Greece</div>
            <h3 class="what green">Intership</h3>
            <div class="when">July 2014 - October 2014</div>
            <p class="description">
                (Intership) Customer Care and Financial Documentation
            </p>
        </li>
        <li class="green">
            <div class="where">Self Employed</div>
            <h3 class="what green">Mathematics Teacher</h3>
            <div class="when">2013 - 2017</div>
            <p class="description">
                Linear Algebra,Geometry,Physics,Differential Equations
            </p>
        </li>
        <li class="green">
            <div class="where">Agile Actors</div>
            <h3 class="what green">Full Stack .NET Developer</h3>
            <div class="when">June 2017 - January 2019</div>
            <p class="description">Banking Sector</p>
        </li>
        <li class="green">
            <div class="where">InTTrust S.A.</div>
            <h3 class="what green">Full Stack .NET Developer</h3>
            <div class="when">January 2019 - Present</div>
            <p class="description">Banking Sector</p>
        </li>
    </ul>
    <!-- <p>
        I have worked for 4+ years in the banking sector for application
        development
    </p>
    <p>
        But in my free time i learn other programming languages so i can enrich
        my prorgamming pallete
    </p> -->
    <!-- <a href="https://github.com/NVasilakop">Check My GitHub Repo :D </a> -->
</main>
