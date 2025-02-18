---
title: Reviewing proposed changes in a pull request
intro: 'In a pull request, you can review and discuss commits, changed files, and the differences (or "diff") between the files in the base and compare branches.'
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request
  - /articles/reviewing-proposed-changes-in-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/reviewing-proposed-changes-in-a-pull-request
  - /github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: Review proposed changes
---
## About reviewing pull requests

You can review changes in a pull request one file at a time. While reviewing the files in a pull request, you can leave individual comments on specific changes. After you finish reviewing each file, you can mark the file as viewed. This collapses the file, helping you identify the files you still need to review. A progress bar in the pull request header shows the number of files you've viewed. After reviewing as many files as you want, you can approve the pull request or request additional changes by submitting your review with a summary comment.

{% data reusables.search.requested_reviews_search_tip %}

## Starting a review

{% webui %}

{% data reusables.repositories.sidebar-pr %}
{% data reusables.repositories.choose-pr-review %}
{% data reusables.repositories.changed-files %}
You can change the format of the diff view in this tab by clicking {% octicon "gear" aria-label="The Settings gear" %} and choosing the unified or split view. The choice you make will apply when you view the diff for other pull requests.

   ![Screenshot of the "Files changed" tab for a pull request. The "Diff view" menu is outlined in dark orange.](/assets/images/help/pull_requests/diff-settings-menu.png)

   You can also choose to hide whitespace differences. The choice you make only applies to this pull request and will be remembered the next time you visit this page.
1. Optionally, filter the files to show only the files you want to review{% ifversion pr-tree-view %} or use the file tree to navigate to a specific file{% endif %}. For more information, see "[AUTOTITLE](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/filtering-files-in-a-pull-request)."
{% data reusables.repositories.start-line-comment %}
{% data reusables.repositories.type-line-comment %}
{% data reusables.repositories.suggest-changes %}
{% ifversion pull-request-comment-on-file %}
{% data reusables.repositories.start-file-comment %}{% endif %}
1. When you're done, click **Start a review**. If you have already started a review, you can click **Add review comment**.

Before you submit your review, your line comments are _pending_ and only visible to you. You can edit pending comments anytime before you submit your review. To cancel a pending review, including all of its pending comments, click **Review changes** above the changed code, then click **Cancel review**.

![Screenshot of the comment field for a review. The "Cancel review" button is outlined in dark orange.](/assets/images/help/pull_requests/cancel-review-button.png)
{% endwebui %}

{% ifversion fpt or ghec %}

{% codespaces %}

You can use [{% data variables.product.prodname_github_codespaces %}](/codespaces/overview) to test, run, and review pull requests.

1. Open the pull request in a codespace, as described in "[AUTOTITLE](/codespaces/developing-in-codespaces/using-github-codespaces-for-pull-requests#opening-a-pull-request-in-codespaces)."
2. In the Activity Bar, click the **GitHub Pull Request** view. This view only appears when you open a pull request in a codespace.

   ![Option to open PR in a codespace](/assets/images/help/codespaces/github-pr-view.png)

3. To review a specific file, click the **Open File** icon in the Side Bar.

   ![Option to open PR in a codespace](/assets/images/help/codespaces/changes-in-files.png)

4. To add review comments, click the **+** icon next to the line number. Type your review comment and then click **Start Review**.

   ![Option to open PR in a codespace](/assets/images/help/codespaces/start-review.png)

5. When you are finished adding review comments, from the Side Bar you can choose to either submit the comments, approve the changes, or request changes.

   ![Option to open PR in a codespace](/assets/images/help/codespaces/submit-review.png)

For more information on reviewing pull requests in {% data variables.product.prodname_github_codespaces %}, see "[AUTOTITLE](/codespaces/developing-in-codespaces/using-github-codespaces-for-pull-requests)."

{% endcodespaces %}
{% endif %}

{% ifversion fpt or ghes or ghec %}
## Reviewing dependency changes

If the pull request contains changes to dependencies you can use the dependency review for a manifest or lock file to see what has changed and check whether the changes introduce security vulnerabilities. For more information, see "[AUTOTITLE](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-dependency-changes-in-a-pull-request)."

{% data reusables.repositories.changed-files %}

1. On the right of the header for a manifest or lock file, display the dependency review by clicking the **{% octicon "file" aria-label="The rich diff icon" %}** rich diff button.

   ![The rich diff button](/assets/images/help/pull_requests/dependency-review-rich-diff.png)

{% data reusables.repositories.return-to-source-diff %}
{% endif %}

## Marking a file as viewed

After you finish reviewing a file, you can mark the file as viewed, and the file will collapse. If the file changes after you view the file, it will be unmarked as viewed.

{% data reusables.repositories.changed-files %}
1. On the right of the header of the file you've finished reviewing, select **Viewed**.

   ![Screenshot of the header of a file. The "Viewed" option is outlined in dark orange.](/assets/images/help/pull_requests/viewed-checkbox.png)

## Submitting your review

After you've finished reviewing all the files you want in the pull request, submit your review.

{% data reusables.repositories.changed-files %}
{% data reusables.repositories.review-changes %}
{% data reusables.repositories.review-summary-comment %}
4. Select the type of review you'd like to leave:

    - Select **Comment** to leave general feedback without explicitly approving the changes or requesting additional changes.
    - Select **Approve** to submit your feedback and approve merging the changes proposed in the pull request.
    - Select **Request changes** to submit feedback that must be addressed before the pull request can be merged.
{% data reusables.repositories.submit-review %}

{% data reusables.repositories.request-changes-tips %}

## Further reading

- "[AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches#require-pull-request-reviews-before-merging)"
- "[AUTOTITLE](/issues/tracking-your-work-with-issues/filtering-and-searching-issues-and-pull-requests)"
