---
title: Bewährte Methoden für die Leistung von Power BI Embedded
description: Dieser Artikel enthält Anleitungen zu bewährten Methoden für Embedded Analytics
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: e28801a15cf50351d737af63bc48f655ca85d28f
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008164"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Bewährte Methoden für die Leistung von Power BI Embedded

Dieser Artikel enthält Empfehlungen zum schnelleren Rendern von Berichten, Dashboards und Kacheln in Ihrer Anwendung

## <a name="embed-parameters"></a>Einbettungsparameter

Die Powerbi.embed()-Methode empfängt einige Parameter zum Einbetten eines Berichts, eines Dashboards oder einer Kachel. Diese Parameter haben Auswirkungen auf die Leistung.

### <a name="embed-url"></a>Einbettungs-URL

Vermeiden Sie es, die Einbettungs-URL selbst zu erstellen. Stellen Sie stattdessen sicher, dass Sie die Einbettungs-URL durch einen Aufruf der API [Get reports](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [Get dashboards](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) oder [Get tiles](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0) abrufen. Wir haben der URL einen neuen Parameter mit der Bezeichnung **_config_** hinzugefügt, der für Verbesserungen der Leistung verwendet wird.

### <a name="permissions"></a>Berechtigungen

Erteilen Sie die Berechtigung **Ansicht**, wenn Sie keinen Bericht im **Bearbeitungsmodus** einbetten möchten. Auf diese Weise initialisiert der Einbettungscode nicht die Komponenten, die für den Bearbeitungsmodus verwendet werden.

### <a name="filters-bookmarks-and-slicers"></a>Filter, Lesezeichen und Slicer

Normalerweise werden Visuals für Berichte mit zwischengespeicherten Daten gespeichert. Aufgrund der zwischengespeicherten Daten verbessert sich die gefühlte Leistung. Berichte können zwischengespeicherte Daten rendern, während die Abfragen ausgeführt werden. Wenn Filter, Lesezeichen oder Slicer angegeben werden, sind die zwischengespeicherten Daten nicht relevant. In diesen Fällen erfolgt das Rendern der Visuals erst nach dem Ausführen der Visual-Abfrage.

Wenn Sie Berichte mit gleichen Filtern einbetten, speichern Sie den Bericht mit bereits angewendeten Filtern, um die Übergabe einer Liste von Filtern in der Ladekonfiguration zu vermeiden.

## <a name="preload"></a>Vorab Laden

Verwenden Sie die JavaScript-API *preload*, um die Endbenutzerleistung zu verbessern.
Powerbi.preload() lädt Javascript, CSS-Dateien und weitere Artefakten herunter, die später für die Einbettung in einem Bericht verwendet werden.

Rufen Sie preload auf, wenn Sie den Bericht nicht sofort einbetten. Wenn Sie beispielsweise einen Bericht auf den Klick auf eine Schaltfläche hin einbetten, ist es sinnvoll, preload während des Ladens der vorhergehenden Seite aufzurufen. Wenn der Benutzer der Anwendung dann auf die Schaltfläche klickt, erfolgt das Rendern schneller.

## <a name="measure-performance"></a>Messen der Leistung

Verwenden Sie zum Messen der Leistung diese Indikatoren:

1. Loaded (Geladen): Zeit bis zur Initialisierung des Berichts (dem Benutzer wird kein Wartekreisel angezeigt).
2. Rendered (Gerendert): Zeit bis zur vollständigen Darstellung des Berichts mit realen Daten. Das Gerendert-Ereignis wird bei jedem erneuten Rendern des Berichts (also nach der Anwendung von Filtern) ausgelöst. Achten Sie bei der erstmaligen Messung eines Berichts darauf, die Berechnungen auf der Grundlage des zuerst ausgelösten Ereignisses durchzuführen.

Zwischengespeicherte Daten werden gerendert, wenn sie verfügbar sind, jedoch gibt es für diese Daten noch kein Ereignis.

## <a name="update-tools-and-sdk-packages"></a>Aktualisieren von Tools und SDK-Paketen

Halten Sie Tools und SDK-Pakete auf dem aktuellen Stand.

* Verwenden Sie immer die aktuellste Version von [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).

* Installieren Sie die aktuellste Version des [Power BI-Client-SDKs](https://github.com/Microsoft/PowerBI-JavaScript). Wir veröffentlichen fortlaufend weitere Verbesserungen, also sehen Sie von Zeit zu Zeit einmal nach.

* Zu installierende Pakete:
    * Npm-Paket: powerbi-client
    * NuGet-Paket: Microsoft.PowerBI.JavaScript

> [!Note]
> Bedenken Sie, dass die Ladezeit in erster Linie von den Elementen abhängt, die für den eigentlichen Bericht und die Daten wichtig sind. Das sind etwa die Anzahl der Visuals, die Größe der Daten und die Komplexität der Abfragen und berechneten Measures. Orientieren Sie sich an den [bewährten Methoden](../power-bi-reports-performance.md), um die Ladezeit des Berichts zu verbessern.

## <a name="next-steps"></a>Nächste Schritte

* [Bewährte Methoden für die Power BI-Leistung](../power-bi-reports-performance.md)
* [Behandeln von Problemen mit Power BI Embedded](embedded-troubleshoot.md)
* [Power BI Embedded – FAQ](embedded-faq.md)