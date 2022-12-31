<script context="module">
    // ^ for server side loading of api requests

    let api_key = ""

    // async means waits for data to be available
    export async function load({fetch }) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${api_key}`);
        const data = await res.json(); // formats it to json
        console.log(data);
        if(res.ok) {
            return {
                props: { popular: data.results }
            }
        }
    }

</script>
