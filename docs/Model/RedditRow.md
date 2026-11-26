# RedditRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subreddit** | **string** | Subreddit name without the r/ prefix; null on a thread whose subreddit is unknown | [optional]
**author** | **string** | Reddit username; null on a thread whose author is unknown | [optional]
**url** | **string** | The subreddit, author profile or thread URL | [optional]
**title** | **string** | Thread title, read from the post or its URL (view&#x3D;threads) | [optional]
**citations** | **int** | Reddit citations of the row in the window | [optional]
**unique_authors** | **int** | Distinct authors cited in the subreddit (view&#x3D;subreddits) | [optional]
**positive** | **int** | Citations in answers with a positive or very positive sentiment | [optional]
**negative** | **int** | Citations in answers with a negative or very negative sentiment | [optional]
**neutral** | **int** | Citations in answers with a neutral sentiment | [optional]
**positive_pct** | **float** | positive over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) | [optional]
**negative_pct** | **float** | negative over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) | [optional]
**yours** | **bool** | Whether the account claims the subreddit or author as its own (on threads, either of them) | [optional]
**subreddits** | **string[]** | The first subreddits the author was cited in (view&#x3D;authors) | [optional]
**extra_subreddits** | **int** | Further subreddits the author was cited in, beyond those listed (view&#x3D;authors) | [optional]
**leaning** | **string** | positive, negative or neutral, whichever sentiment has more of the author&#39;s citations (view&#x3D;authors) | [optional]
**brands** | [**\LLMPulse\Model\RedditAuthorBrand[]**](RedditAuthorBrand.md) | Brands the content of the author&#39;s cited posts names, your own first (view&#x3D;authors) | [optional]
**subreddit_yours** | **bool** | Whether the account claims the thread&#39;s subreddit (view&#x3D;threads) | [optional]
**author_yours** | **bool** | Whether the account claims the thread&#39;s author (view&#x3D;threads) | [optional]
**latest_cited_at** | **\DateTime** | The thread&#39;s most recent citation (view&#x3D;threads) | [optional]
**upvotes** | **mixed** | Upvotes as the scraped post reports them, a number or a numeric string, or null when unknown (view&#x3D;threads) | [optional]
**comments** | **mixed** | Comment count as the scraped post reports it, a number or a numeric string, or null when unknown (view&#x3D;threads) | [optional]
**avg_position** | **float** | Average rank of the thread&#39;s citations, 1 &#x3D; first; null when no citation has a visible rank (view&#x3D;threads) | [optional]
**sentiment** | **string** | The most frequent sentiment of the answers that cite the thread; null when none is rated (view&#x3D;threads) | [optional]
**archived** | **mixed** | Whether the thread is archived as the scraped post reports it, usually a boolean, or null when unknown (view&#x3D;threads) | [optional]
**posted_at** | **\DateTime** | When the thread was posted; null when unknown (view&#x3D;threads) | [optional]
**breakdown** | **string** | sentiment, model or country (view&#x3D;breakdowns) | [optional]
**key** | **string** | The slice, a sentiment label, a model or an uppercase country code (view&#x3D;breakdowns) | [optional]
**count** | **int** | Reddit citations in the slice (view&#x3D;breakdowns) | [optional]
**pct** | **float** | Share of the slice within its breakdown, 0-100 (view&#x3D;breakdowns) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
