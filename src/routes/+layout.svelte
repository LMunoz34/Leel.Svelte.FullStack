<script lang="ts">
    import { FirebaseApp } from 'sveltefire';
    import { initializeApp } from 'firebase/app';
    import { getFirestore } from 'firebase/firestore';
    import { getAuth } from 'firebase/auth';
    import { firebaseconfig } from '../lib/firebase.js';
    //import {app} from '../lib/firebase.js';

    // Initialize Firebase
    const app = initializeApp(firebaseconfig);
     const firestore = getFirestore(app);
    const auth = getAuth(app);
</script>

<FirebaseApp {auth} {firestore}>
    <slot />
</FirebaseApp>