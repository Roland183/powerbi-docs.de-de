---
title: Verwenden von Slicern in Power BI Desktop
description: "Sie können Slicer in Power BI Desktop für das Filtern, Hervorheben und Anpassen von Berichten verwenden."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: 107b4eace4e5b10b52900a4d15110c8acad0f462
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="using-slicers-power-bi-desktop"></a>Verwenden von Slicern in Power BI Desktop

Sie können einen **Slicer** in **Power BI Desktop** verwenden, um die Ergebnisse von Visuals auf Ihrer Berichtsseite zu filtern. Mithilfe von Slicern können Sie den angewendeten Filter einfach anpassen, indem Sie mit dem Slicer interagieren. Sie können ebenfalls Optionen dafür angeben, wie Ihr Slicer angezeigt wird und wie Sie mit diesem interagieren. Die folgende Abbildung stellt einen Slicer dar, dessen Dropdownmenü für *Typen* angezeigt wird. 

![](media/desktop-slicers/desktop-slicers_01.png)

Ein Slicer kann für folgende Typen angezeigt werden:

* Liste (List)
* Dropdown
* Zwischen
* Kleiner als oder gleich
* Größer als oder gleich

Sie können einen Slicer zu einem Bericht hinzufügen, indem Sie auf das Visual **Slicer** im Bereich **Visualisierungen** klicken.

![](media/desktop-slicers/desktop-slicers_02.png)

Das Verhalten von Slicern ist in **Power BI Desktop** und im **Power BI-Dienst** ähnlich. Ein Tutorial zur Verwendung von Slicern finden Sie unter [Slicer im Power BI-Dienst (Tutorial)](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Synchronisieren von Slicern über mehrere Berichtsseiten

In **Power BI Desktop** können Sie Slicer über mehrere Berichtsseiten synchronisieren. Klicken Sie im Bereich **Ansicht** im Menüband auf **Slicer synchronisieren**, um Slicer zu synchronisieren. Wenn Sie Slicers synchronisieren, wird der Bereich **Slicer synchronisieren** wie in der folgenden Abbildung dargestellt angezeigt.

![](media/desktop-slicers/desktop-slicers_03.png)

Im Bereich **Slicer synchronisieren** können Sie angeben, wie der Slicer über mehrere Berichtsseiten synchronisiert werden soll. Sie können angeben, ob jeder Slicer auf jede einzelne Berichtsseite **angewendet** werden soll und ob der Slicer auf jeder einzelnen Berichtsseite **sichtbar** sein soll.

Sie können einen Slicer wie in der folgenden Abbildung dargestellt beispielsweise auf **Seite 2** Ihres Berichts platzieren. Sie können dann auswählen, ob dieser Slicer für jede ausgewählte Seite *gelten* soll und ob der Slicer auf jeder ausgewählten Seite im Bericht *sichtbar* sein soll. Für jeden Slicer können Sie eine beliebige Kombination dieser Optionen anwenden. 

![](media/desktop-slicers/desktop-slicers_04.png)

Durch den Link **Allen hinzufügen** in diesem Bereich wird der ausgewählte Slicer auf alle Seiten im Bericht angewendet.

Beachten Sie, dass die Auswahl, die im Bereich **Slicer synchronisieren** angezeigt wird, nur für den *ausgewählten Slicer* gilt. Sie können mehrere Slicer auf verschiedene Seiten anwenden und den Bereich verwenden, um zu definieren, wie jeder Slicer auf die verschiedenen Seiten Ihres Berichts angewendet wird. 

Die Auswahl der Slicer kann synchronisiert werden, andere Auswahlen wie die Formatierung, die Bearbeitung und das Löschen werden jedoch *nicht* synchronisiert. 

## <a name="next-steps"></a>Nächste Schritte

Folgende Artikel könnten Sie ebenfalls interessieren:

* [Slicer im Power BI-Dienst (Tutorial)](power-bi-visualization-slicers.md)
* [Verwenden der Funktion „Slicer für numerischen Bereich“ in Power BI Desktop](desktop-slicer-numeric-range.md)
* [Verwenden eines relativen Slicers mit Datum und eines relativen Datumsfilters in Power BI Desktop](desktop-slicer-filter-date-range.md)
