---
title: Optimieren Ihrer Excel-Daten für Q&A in Power BI
description: Optimieren Ihrer Daten für Q&A in Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 627a94097d4235f39414c1165ac8cbbc806508a3
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430055"
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Optimieren Ihrer Excel-Daten für Q&A in Power BI
Wenn Sie Datenmodelle oder Excel-Arbeitsmappen erstellen, die mit Power BI verwendet werden, lesen Sie weiter...

Q&A kann in Power BI strukturierte Daten suchen und die richtige Visualisierung für Ihre Frage auswählen – genau diese Funktion macht Power BI zu einem so überzeugenden Tool.   

Q&A funktioniert mit allen hochgeladenen Excel-Dateien, die Tabellen, Bereiche oder PowerPivot-Modelle enthalten. Je häufiger Sie optimieren und Ihre Daten bereinigen, desto robuster wird die Q&A-Leistung.  Wenn Sie beabsichtigen, auf dem Dataset basierende Berichte und Dashboards freizugeben, möchten Sie, dass Ihre Kollegen bequem Fragen stellen können und aufschlussreiche Antworten erhalten.

### <a name="how-qa-works-with-excel"></a>Funktionsweise von Q&A mit Excel
Q&A verfügt über eine Reihe grundlegender Funktionen zum Verstehen natürlicher Sprachen, die Sie für Ihre Daten anwenden können. Es verfügt über eine kontextabhängigen Schlüsselwortsuche für Ihre Excel-Tabelle, die Spalte und die berechneten Feldnamen. Außerdem weiß das Programm, wie Daten gefiltert, sortiert, zusammengeführt, gruppiert und angezeigt werden sollen. 

In einer Excel-Tabelle mit dem Namen „Verkauf“ mit den Spalten „Produkt“, „Monat“, „Verkaufte Einheiten“, „Bruttoumsatz“ und „Gewinn“ können Sie beispielsweise Fragen zu diesen Entitäten stellen.  Sie können beispielsweise die Umsätze oder den Gesamtgewinn pro Monat anzeigen, die Produkte nach verkauften Einheiten sortieren usw. Erfahren Sie mehr über die [Arten möglicher Fragen](consumer/end-user-q-and-a.md) und die [Visualisierungstypen, die Sie in einer Abfrage in Q&A angeben können](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

### <a name="prepare-an-excel-dataset-for-qa"></a>Vorbereiten eines Excel-Datasets für Q&A
Q&A stützt sich auf die Namen der Tabellen, Spalten und berechneten Felder, um datenspezifische Fragen zu beantworten. Daher sind die Bezeichnungen der Entitäten in Ihrer Arbeitsmappe von großer Bedeutung.

Hier finden Sie einige Tipps zur optimalen Nutzung von Q&A in der Arbeitsmappe.

* Stellen Sie sicher, dass Ihre Daten in einer Excel-Tabelle gespeichert sind. [So erstellen Sie eine Excel-Tabelle](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Stellen Sie sicher, dass die Tabellen, Spalten und berechneten Felds sinnvoll in natürlicher Sprache benannt sind.
  
  Wenn Sie z. B. eine Tabelle mit Verkaufsdaten haben, nennen Sie die Tabelle „Vertrieb“. Spaltennamen wie „Jahr“, „Produkt“, „Vertriebsmitarbeiter“ und „Betrag“ funktionieren in Q&A sehr gut.

* Wenn die Arbeitsmappe ein PowerPivot-Datenmodell aufweist, können Sie noch mehr Optimierungen durchführen. Unter [Demystifying Power BI Q&A Part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) erhalten Sie von unserem Expertenteam für natürliche Sprachen weitere Informationen.

* Öffnen Sie das Dataset in Power BI Desktop, und erstellen Sie neue Spalten, erstellen Sie berechnete Measures, verketten Sie Felder, um eindeutige Werte zu erstellen, klassifizieren Sie Daten nach Typ (z.B. Datumsangaben, Zeichenfolgen, Geografie, Bilder, URLs), und führen Sie weitere Aktionen aus.

## <a name="next-steps"></a>Nächste Schritte
Zurück zu [Q&A in Power BI](consumer/end-user-q-and-a.md)  
[Vorbereiten lokaler Datasets für Q&A](service-q-and-a-direct-query.md)   
[Q&A-Schnellstart](power-bi-visualization-introduction-to-q-and-a.md)  
[Abrufen von Daten (für Power BI)](service-get-data.md)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

