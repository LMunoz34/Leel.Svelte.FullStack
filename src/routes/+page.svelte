<script>
  import { SignedIn, SignedOut, Doc, Collection } from 'sveltefire';
  import { signInAnonymously, signInWithPopup, GoogleAuthProvider } from "firebase/auth";
  var provider = new GoogleAuthProvider();
</script>
<style>
    .centered-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 100vh;
        background-color: teal;
        padding: 0 20px;
    }

    .auth-section {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
        /* This ensures the auth section doesn't grow but the posts section does */
        flex: 0 0 auto; 
    }

    h3 {
        color: white;
        margin: 0;
    }

    button {
        background-color: white;
        color: teal;
        border: none;
        padding: 10px 20px;
        cursor: pointer;
        border-radius: 5px;
        transition: background-color 0.3s ease;
        font-weight: bold;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    button:hover {
        background-color: rgba(255,255,255, 0.8);
    }

    .posts-container {
        display: flex;
        flex-direction: column;
        gap: 20px;
        background-color: white;
        padding: 20px;
        border-radius: 10px;
        /* This allows the posts container to grow as needed */
        flex-grow: 1;
        width: 450px;
    }

    .card {
        padding: 10px;
        border-radius: 5px;
        background-color: teal;
        color: white;
        transition: transform 0.1s ease;
    }

    .card:hover {
        transform: scale(1.03); /* this will make the card grow by 10% */
    }

    p {
        color: #fff;
    }

</style>

<div class="centered-container">
    <div class="auth-section">
        <h3><b>Leel.Svelte.FullStack</b></h3>
        <SignedIn let:user let:signOut>
            <p>Hello {user.uid}</p>
            <button on:click={signOut}>Sign Out</button>
        </SignedIn>

        <SignedOut let:auth>
            <button on:click={() => signInWithPopup(auth, provider)}>Sign In</button>
        </SignedOut>
    </div>

    <div>
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
    </div>
</div>
