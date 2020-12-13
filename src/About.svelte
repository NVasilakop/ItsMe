<script>
    import { Router, Route, Link } from "svelte-routing";
    import Avatar from "svelte-avatar";
    export let url = ""; //This property is necessary declare to avoid ignore the Router
    import IconifyIcon from "@iconify/svelte";
    import linkedinWithCircle from "@iconify-icons/entypo-social/linkedin-with-circle";
    import gitHubWithCircle from "@iconify-icons/entypo-social/github-with-circle";
    import { Button } from "sveltestrap";

    let pageName = "About Me";
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
</style>

<main>
    <h1>{pageName}!</h1>
    <p>So who am I</p>
    <div>
        <Avatar
            name="Nick Vasilakopoulos"
            size="200px"
            style=" margin-left: auto;
                 margin-right: auto;
                width: 10%;"
            src="assets/itsMe.jpg" />

        <p>
            I am Nick Vasilakopoulos a Software Engineer from Greece,originally
            from Aigio and living now in Athens
        </p>
    </div>
    <p>
        Currently i am working as a Full Stack Developer (SQL,.NET,.NET
        Core,Angular 9)
    </p>

    <Router {url}>
        <!-- <nav>
            <Link to="studies">Studies</Link>
            <Link to="work">Work</Link>
            <Link to="interests">Interests</Link>
        </nav> -->
        <div>
            <!-- <Route path="work" component={Work} /> -->
            <!--for now the router just support case sensitive,
        one workaround colud be add two time the route
        Example.
       <Route path="About" component="{About}" /> 
    -->
        </div>
    </Router>
</main>
