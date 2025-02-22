---
title: Estimate connection size
description: Report on your current usage of Customer Journey Analytics
---

# Estimate connection size

You may need to know how many rows of data you currently have in [!UICONTROL Customer Journey Analytics]. The purpose of this topic is to show you how to report on your current usage of [!UICONTROL Customer Journey Analytics].

1. In [!UICONTROL Customer Journey Analytics], click the **[!UICONTROL Connections]** tab.
1. On the [!UICONTROL Edit connection] screen, select a connection for which you want to determine the usage/connection size.

    ![Edit connection](assets/edit-connection.png)

1. Select a dataset that is your part of the connection from the left rail. In this case, it is the "B2B Impression" dataset.

    ![dataset](assets/dataset.png)

1. Click the blue (i) icon (info) next to its name. You will notice the dataset has 3.8k rows/events. In addition, for the exact number of rows, click **[!UICONTROL Edit in Experience Platform]** below the preview table. This will redirect you to the datasets in [!UICONTROL Adobe Experience Platform].

    ![AEP dataset info](assets/data-size.png)

1. Notice the **[!UICONTROL Total records]** for this dataset amount to 3.83k records, with the size of the data being 388.59 KB.

1. Repeat steps 1-5 for other datasets in your connection and add up the number of records/rows. The final aggregated number will be the usage metric of your connection. This is the number of rows of the datasets of your connection which you are going to ingest from [!UICONTROL Adobe Experience Platform]. 

## Determine number of rows ingested

The number of events actually ingested in [!UICONTROL Customer Journey Analytics] depends upon your connection configuration settings. In addition, if you selected the wrong Person ID or if this ID is not available for some rows in the datasets, then [!UICONTROL Customer Journey Analytics] will ignore those rows. In order to determine the actual rows of events ingested, take the following steps:

1. Once you save the connection, create a data view of the same connection without any filters.
1. Create a Workspace project and select the correct data view. Create a freeform table and drag and drop the **[!UICONTROL Events]** metric with a **[!UICONTROL Year]** dimension. Choose a large enough date range from your date selection calendar to encapsulate all of the data in your connection. This allows you to see the number of events being ingested into [!UICONTROL Customer Journey Analytics].

    ![Workspace project](assets/event-number.png)

    >[!NOTE]
    >
    >This lets you see the number of events being ingested from your events dataset. It does not include profile and lookup type datasets. Follow steps 1-3 under "Estimate connection size" for profile and lookup datasets and add up the numbers to get the  total number of rows for this connection.

## Diagnose discrepancies

In some cases, you may notice that the total number of events ingested by your connection is different than the number of rows in the dataset in [!UICONTROL Adobe Experience Platform]. In this example, the dataset "B2B Impression" has 7650 rows, but the dataset contains 3830 rows in [!UICONTROL Adobe Experience Platform]. There are several reasons why discrepancies can happen, and the following steps can be taken to diagnose:

1. Break down this dimension by **[!UICONTROL Platform Dataset ID]** and you will notice two datasets with same size but different **[!UICONTROL Platform Dataset IDs]**. Each dataset has 3825 records. That means [!UICONTROL Customer Journey Analytics] ignored 5 records due to missing person IDs or missing timestamps:

    ![breakdown](assets/data-size2.png)

1. In addition, if we check in [!UICONTROL Adobe Experience Platform], there is no dataset with Id "5f21c12b732044194bffc1d0", hence someone deleted this particular dataset from [!UICONTROL Adobe Experience Platform] when the initial connection was being created. Later it got added to [!UICONTROL Customer Journey Analytics] again, but a different [!UICONTROL Platform Dataset ID] was generated by [!UICONTROL Adobe Experience Platform]. 

    Read more about the [implications of dataset and connection deletion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) in [!UICONTROL Customer Journey Analytics] and [!UICONTROL Adobe Experience Platform].
