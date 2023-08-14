<script>
  import { SignedIn, SignedOut, Doc, Collection } from 'sveltefire';
  import { signInAnonymously, signInWithPopup, GoogleAuthProvider } from "firebase/auth";
  var provider = new GoogleAuthProvider();
</script>

<div class="posts-container">
    <h3><b>Leel.Svelte.FullStack</b></h3>

    <SignedIn let:user let:signOut>
        <p>Hello {user.uid}</p>
        <button on:click={signOut}>Sign Out</button>
    </SignedIn>

    <SignedOut let:auth>
        <button on:click={() => signInWithPopup(auth, provider)}>Sign In</button>
    </SignedOut>
</div>
<!-- <Doc ref="posts/D95x9JWsDn0mxpzpvQVS" let:data>
    <h2>{data.title}</h2>
    <p>{data.content}</p>
</Doc> -->

<Collection ref="posts" let:data={posts}>
    <div class="posts-container">
        {#each posts as post}
            <div class="card">
                <h2>{post.title}</h2>
                <p>{post.content}</p>
            </div>
        {/each}
    </div>
</Collection>

