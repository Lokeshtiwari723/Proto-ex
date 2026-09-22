# Retrospective

My goal was to build practical AI/ML work that turns data into useful decisions. The project developed around Ranking Signal Analysis, with the practical question of how a content or SEO reviewer could decide which pages to inspect first.

The biggest change in my approach was moving from a broad idea to a defined decision-support problem. I identified the unit of analysis, selected observable signals, and separated the proxy target from the model features. The selected signals were impressions, clicks, average position, word count, and content age. I used trend direction to construct a proxy label and excluded it from the feature set.

The validation work also changed how I think about model results. Instead of treating a single score as proof, I used a grouped split by client and checked that train and test clients did not overlap. The recorded split had 75,670 training rows and 10,890 test rows, with 29 train clients and 8 test clients and zero client overlap.

The recorded results provided a useful comparison. The Week-4 baseline had Precision@50 of 0.76, while Logistic Regression reached 1.00 Precision@50 on the tested split. I do not treat this as proof of a production-ready system. Many positive pages still remained outside the top 50, so the ranking is better understood as a way to prioritize human review rather than as a complete detector.

I also moved the work beyond the notebook by building a public portfolio. The portfolio includes the Ranking Signal Analysis work and a working contact form using Netlify Forms. I tested the form with a real submission and confirmed that the submission appeared in the Netlify Forms dashboard.

Three transferable lessons were especially important: define the decision before choosing the model; separate evidence from assumptions and avoid claiming more than the evaluation supports; and connect technical work to a clear user action.

If I continued the project, I would test the ranking on additional data and evaluate whether the ordering remains useful for real reviewers. I would also investigate pages that remain outside the top 50 and whether additional signals improve the review queue without introducing leakage.

AI assistance was used for planning and documentation, while the project claims are grounded in the notebook outputs and work that was checked.
