<script>
    let pageName = "Hello There";
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
    html {
        height: 100%;
    }

    body {
        margin: 0;
    }

    .bg {
        animation: slide 3s ease-in-out infinite alternate;
        background-image: linear-gradient(-60deg, #6c3 50%, #09f 50%);
        bottom: 0;
        left: -50%;
        opacity: 0.5;
        position: fixed;
        right: -50%;
        top: 0;
        z-index: -1;
    }

    .bg2 {
        animation-direction: alternate-reverse;
        animation-duration: 4s;
    }

    .bg3 {
        animation-duration: 5s;
    }

    .content {
        background-color: rgba(255, 255, 255, 0.8);
        border-radius: 0.25em;
        box-shadow: 0 0 0.25em rgba(0, 0, 0, 0.25);
        box-sizing: border-box;
        left: 50%;
        padding: 10vmin;
        position: fixed;
        text-align: center;
        top: 25%;
        transform: translate(-50%, -50%);
    }

    h1 {
        font-family: monospace;
    }

    @keyframes slide {
        0% {
            transform: translateX(-25%);
        }
        100% {
            transform: translateX(25%);
        }
    }
</style>

<main>
    <div class="bg" />
    <div class="bg bg2" />
    <div class="bg bg3" />
    <div id="puns-container" class="content">
        <div class="row">
            <code>{`if(wayToHapiness.IsNullOrEmpty())`}</code>
        </div>
        <div class="row">
            <code>{`.happy-life { contains: content; }`}</code>
        </div>
        <div class="row">
            <code>{`.stayathome { visibility: hidden; }`}</code>
        </div>
        <div class="row">
            <code>{`printf("Going to be an awesome day");`}</code>
        </div>
        <div class="row"><code /></div>
    </div>
</main>
