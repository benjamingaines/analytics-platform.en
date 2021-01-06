---
title: Customer Journey Analytics feature support
description: Customer Journey Analytics features compared with Adobe Analytics features set.
---

# Customer Journey Analytics feature support

The following tables list which features in Adobe Analytics are supported, partially supported or not supported in Customer Journey Analytics (CJA). These lists will change over time as features are added to CJA.

## Fully supported features/components

| Feature | Notes |
| --- | --- |
| Metrics | CJA leverages the Experience Data Model (XDM) and supports unlimited metrics and is not tied to the custom success events of traditional Analytics. Note that some standard metrics have been renamed from traditional Analytics: Visitors = People, Visits = Sessions, Hits = Events. |
| Dimensions | CJA leverages XDM and supports unlimited dimensions and is not tied to the custom success events of traditional Analytics. |
| List Variables/List Props | CJA leverages XDM and supports unlimited list variables |
| Date Ranges | Custom Calendar support is planned. |
| Calculated Metrics | Note that any existing calc metrics in the traditional Analysis Workspace will not be ported to CJA. |
| Segments | Now called "Filters" - note that any existing segments in traditional Analysis Workspace will not be ported to CJA. |
| Anomaly Detection | Full Support |
| Attribution IQ | Full Support |
| Project Curation | Full Support |
| Project Linking | Full Support |
| Date Comparisons | Full Support |
| Virtual Report Suites | Now called [Data Views](/help/data-views/create-dataview.md). |
| VRS Component Curation | Now part of Data Views. |
| Report Time Processing | CJA relies exclusively on Report Time Processing. |
| GDPR Deletion | Note that GDPR is now handled in coordination with [!UICONTROL Experience Platform] - CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |
| User Permissions/Data Access Controls | CJA distinguishes between Adobe Admin Console product admins and users. Only product admins are able to 1) create/update/delete Connections or Data Views, 2) update/delete projects, filters, or calc metrics that were created by other users, and 3) share a Workspace project to all users |

## Supported with caveats

| Feature | Notes |
| --- | --- |
| Product Variable | The product variable currently available for reporting for data conforming to the Experience Event schema (specifically using the productListItems object). |
| Marketing Channels | Marketing Channels data now flows into CJA through the Analytics Data Connector. Marketing Channel rules must still be configured in traditional Adobe Analytics. Some rules are not supported. For more details, please see [CJA Marketing Channels documentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases) |
| Visualizations | All visualizations are supported except for the Map visualization. |
| Project Sharing | Project sharing is only supported between users of CJA - there is not project sharing between CJA and the traditional Analysis Workspace. |
| Custom Sessionization | Support for all custom sessionization features other than mobile background hits. |
| eVar persistence settings | eVars are no longer part of CJA. However, persistence settings are now part of Data Views and are available for all dimensions. Keep in mind that persistence is based on report time processing, not data collection processing. This means all persistence will be based on the reporting date range rather than the entirety of the data. |
| Classifications | Now called "Lookup Datasets", they do not get automatically imported from traditional Analytics. They will have to be uploaded to AEP before they're available in CJA. |
| Customer Attributes | Now called "Profile Datasets", they do not get automatically imported from Experience Cloud, but will have to be uploaded to AEP before they're available in CJA. |
| Device, Browser, Technology dimensions | These dimensions are automatically included when an AEP dataset includes specific XDM schema fields and conforms to the XDM Experience Event class. |
| Entries, Exits, and Timespent dimesions and metrics | Supported (Entries and Exits are now called Session Starts and Session Ends) and are calculated in a slightly different way. |

## Partial Support

| Feature | Notes |
| --- | --- |
| Out-of-the-box Analysis Workspace dimensions (e.g. Browser Type, Referrer Type, Marketing Channels, Visit Number etc.) | CJA does not provide these dimensions natively. For customers using the Analytics Data Connector (ADC), some of these dimensions are available, but not all. Please refer to our [documentation on which Analytics variables are supported via ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Panels | Blank Panel, Attribution Panel, Freeform Panel, and Quick Insights are fully supported. The Segment Comparison, Analytics for Target (A4T), and Media Concurrent Viewers panels are not supported. |
| Merchandising eVars | Merchandising eVars will only work with ADC-based datasets unless they strictly conform to the same XDM schema (similar to the product list limitations above). |
| Bot Filtering | For Analytics Data Connector (ADC)-based datasets, bot filtering is applied. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| Processing Rules | For ADC-based datasets, processing rules are still applied. |
| Cross-Device Identity Stitching | Customers are limited to "one-time" stitches of the data via Query Service, or currently must apply this logic to data prior to [!UICONTROL Experience Platform] data ingestion. |

## Not currently supported, but planned

| Feature | Notes |
| --- | --- |
| Contribution Analysis | Support is planned. |
| Segment IQ | Support is planned. |
| Report Builder (Excel plugin) | Support is planned. |
| Segment Publishing (sending segments from Workspace to the Experience Cloud) | Support is planned. |
| CSV download | Support is planned. |
| Real-Time Reporting | Support is planned. |
| Metric deduplication | Support is planned. |
| Custom Calendars | Support is planned. |
| Metric deduplication | Support is planned. |
| Merchandising variable persistence | Support is planned. |
| Scheduled Reports/Projects | Support is planned. |
| Alerts | Support is planned. |
| Custom Calendars | Support is planned. |
| PDF Export | Support is planned. |
| Reporting API Access | Support is planned - will only be available with API 2.0. |
| ID Stitching via Device Graph | Support is planned. |

## Support not yet planned

| Feature | Notes |
| --- | --- |
| A4T | Support is not yet planned. |
| Media Analytics | Support is not yet planned. |
| Advertising Cloud | Support is not yet planned. |
| Activity Map | Support is not yet planned. |
| Classification Rule Builder | Support is not yet planned. |
| Summary Data Sources | Support is not yet planned. |

## Will never be supported

* People metric using Cross-Device Coop
* Reports & Analytics Dashboards
* Reports & Analytics Bookmarks
* Reports & Analytics Targets
* Reports & Analytics Calendar Events
* Ad Hoc Analysis
* Data Warehouse Reporting - [!UICONTROL Experience Platform Query Service] will be the new interface for these use cases in CJA.
* Mobile Services
* Data Feeds
