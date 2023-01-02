<script context="module">
    // ^ for server side loading of api requests


    // async means waits for data to be available
    console.log(`${import.meta.env.VITE_API}`)
    export async function load({fetch }) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_API} `);
        const data = await res.json(); // formats it to json
        console.log(data);
        if(res.ok) {
            return {
                props: { popular: data.results }
            }
        }
    }

</script>


<p>Movie Goggles</p>