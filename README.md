# Fair Microlending System
This repository contains a fair recommendation system for microfinance loans called JARFIS: Just A Rather Fair Investment System. 

# Motivation
Microfinance has been proven to be an efficient method to help businesses in impoverished countries
get loans which may otherwise be difficult to obtain from the traditional financial institutions. An
important question in microlending is how to efficiently connect potential borrowers and lenders.
Most recommendation systems nowadays use the collaborative filtering technique, recommending
items to a user based on behavioral patterns of similar users. This paradigm, however, emphasizes
individual preference but ignores fairness of different groups in the system. The focus of the project was 
to promote personalized fairness to borrowers in the recommendation system, which
means that loans requested by borrowers from different demographic backgrounds are equally likely
to be recommended to active lenders.

# Considerations
Loan recommendation poses unique challenges compared to other recommendations because
of two attributes: loans are often one-time commitments and when lenders do not endorse a loan, it is
not clear whether it is because they have no interests or have not yet viewed the loans. This issue can be solved
by first transforming loans into pseudo-items using
content-based techniques and then retaining only lenders who had funded at least 5 pseudo-items
and pseudo-items with at least 5 funders. For the sparsity
problem, loans were grouped by their features: borrower gender, borrower country, loan sector, etc.,
and the total number of lender-item pairs were counted for each feature. Loans were then clustered to simplify the
model, using agglomerative clustering. For the implicit feedback problem, we followed the latent
factor model and included a neighborhood fairness term in the Alternating Least Square (ALS) cost
function. We used techniques like gradient descent to update preferences for user-item pairs, based
on preferences in previous iterations.
