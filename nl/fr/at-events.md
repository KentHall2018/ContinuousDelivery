---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-29"

keywords: Activity Tracker events, tool-instance, List of events

subcollection: ContinuousDelivery

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:table: .aria-labeledby="caption"}

<!-- Name your file `at-events.md` and include it in the Reference nav group in your toc file. -->

# Evénements {{site.data.keyword.cloudaccesstrailshort}}
{: #at_events}

Utilisez le service {{site.data.keyword.cloudaccesstrailfull}} pour savoir comment les utilisateurs et les applications interagissent avec le service {{site.data.keyword.contdelivery_short}} dans {{site.data.keyword.Bluemix}}. 
{: shortdesc}

Le service {{site.data.keyword.cloudaccesstrailfull_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations, voir [{{site.data.keyword.cloudaccesstrailshort}}](/docs/services/cloud-activity-tracker?topic=cloud-activity-tracker-getting-started).

<!-- You can create different sections to group events by area. -->

## Liste des événements
{: #events}

Le tableau suivant répertorie les actions qui génèrent un événement :

| Action | Description | 
|:-----------------|:-----------------|
| continuous-delivery.toolchain.create | Créer une chaîne d'outils | 
| continuous-delivery.toolchain.delete | Supprimer une chaîne d'outils |
| toolchain.tool-instance.deploy | Créer une intégration d'outils |
| toolchain.tool-instance.undeploy | Supprimer une intégration d'outils |
{: caption="Tableau 1. Actions qui génèrent des événements" caption-side="top"}

## Emplacement des événements
{: #ui}

<!-- Option 2: Add the following sentence if your service sends events to the account domain. -->

Les événements {{site.data.keyword.cloudaccesstrailshort}} sont disponibles dans le **domaine de compte** {{site.data.keyword.cloudaccesstrailshort}} qui se trouve dans la région {{site.data.keyword.Bluemix_notm}} où les événements sont générés.
