<script lang="ts">
	import type { Book } from "$lib/state/user-state.svelte";
	import BookCard from "./BookCard.svelte";

    interface BookCategoryProps {
        categoryName: string;
        booksToDisplay: Book[];
    }

    let { categoryName, booksToDisplay }: BookCategoryProps = $props();
</script>

<section class="book-category">
    <h3 class="mb-s">Your most loved books</h3>
    <div class="books-container">
        {#each booksToDisplay as book }
            <BookCard {book} />
        {/each}
    </div>
</section>