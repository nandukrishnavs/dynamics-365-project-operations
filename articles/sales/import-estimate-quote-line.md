---
title: Import estimates for a project to a project-based quote line
description: This topic provides information about importing estimates from a project to a quote line.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Import estimates for a project to a project-based quote line

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


If a project is created during the pre-sales stage, you can select to import the financial estimate from the project to the project-based quote line.

1. Make sure that the project-based quote line has the project information in the **Project** field.
2. On the **Quote line details** tab, select **Import from Project Estimation**.
3. On the dialog page opens, select one of the following summarization options.

  - **Transaction class**
  - **Category**
  - **Role** 
  - **Project task**

Based on your selection, the estimate from the project for all transaction classes included on this quote line are copied over. To check what transaction classes are included, select the **General** tab on the project-based quote line, and check the values for **Include Time**, **Include Expenses**, and **Include Fees**.

When you import estimates, the system will default the pricing based on the project price lists attached to the quote and the billing type set up on the project-based quote line. If a role or category is set up on the project-based quote line as non-chargeable, the imported estimate line will set as non-chargeable and won't add up to the quoted value of quote line.

When a quote line has line details, the **Quote Value** and the **Estimated Tax** fields on the quote line are summarized and can't be edited.

When multiple summarization options are selected, the summarization attempts to summarize by all selected options. This means that the output of imported quote lines will be more than if you selected only one summarization option.

For example, If the project has the following estimate lines for expenses.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

When the user selects to summarize by Transaction class, the following information will be imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| | | 10/1/2020 | 3.34 | 840 | 2800 |

When the user selects to summarize by Transaction class and Category, the following information will be imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| | Hotel | 10/1/2020 | 6 | 200 | 1200 |

When the user selects to summarize by Transaction class, Category, and Leaf Node Task, the following information will be imported. Notice that this result is the same as what was on the project.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |