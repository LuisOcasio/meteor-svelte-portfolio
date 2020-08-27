<script>
  import { useTracker } from "meteor/rdb:svelte-meteor-data";
  import { Likes } from "../api/likes";
  import Landing from './pages/landing.svelte'

  let newLike = Boolean;

  $: likes = useTracker(() =>
    Likes.insert({
      liked: newLike,
    })
  );

  function handleSubmit(event) {
    Resolutions.insert({
      liked: newLike,
    });
    newRes = Boolean;
  }
</script>

<main>
  <Landing/>
</main>
