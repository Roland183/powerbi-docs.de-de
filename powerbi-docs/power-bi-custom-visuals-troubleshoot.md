---
title: Problembehandlung bei der Entwicklung von benutzerdefinierten Power BI-Visuals
description: In diesem Artikel werden einige häufige Probleme erläutert, die beim Entwickeln oder Erstellen eines benutzerdefinierten Power BI-Visuals auftreten können.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: 252b980b3a10bbafc29c36ad249b23166fb514f1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286563"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Problembehandlung bei benutzerdefinierten Power BI-Visuals

## <a name="debug"></a>Debuggen

**Pbiviz-Befehl wurde nicht gefunden (oder ähnliche Fehler)**

Wenn Sie `pbiviz` über die Befehlszeile Ihres Terminals ausführen, sollte das Hilfefenster angezeigt werden. Wenn dies nicht der Fall ist, war die Installation fehlerhaft. Stellen Sie sicher, dass Sie mindestens Version 4.0 von NodeJS installiert haben.

**Das Debug-Visual wird nicht auf der Registerkarte „Visualisierungen“ angezeigt**

Die Debug-Visualisierung sieht wie ein Eingabeaufforderungssymbol auf der Registerkarte **Visualisierungen** aus.

![Auswahl des Visuals](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Wenn sie nicht angezeigt wird, vergewissern Sie sich, dass Sie sie in den Power BI-Einstellungen aktiviert haben.

> [!NOTE]
> Die Debug-Visualisierung ist derzeit nur im Power BI-Dienst und nicht in Power BI Desktop oder in der mobilen App verfügbar. Die gepackte Visualisierung kann aber überall ausgeführt werden.

**Server für visuelle Elemente kann nicht erreicht werden**

Führen Sie den Server für Visuals mit dem Befehl `pbiviz start` über die Befehlszeile Ihres Terminals im Stammverzeichnis des Visualprojekts aus. Wenn der Server nicht ausgeführt wird, wurden vermutlich die SSL-Zertifikate nicht ordnungsgemäß installiert.

Zögern Sie nicht, sich mit Fragen, Kommentaren oder Problemen an das Supportteam für benutzerdefinierte Visuals zu wenden: *pbicvsupport@microsoft.com* .

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen finden Sie in den [häufig gestellten Fragen zu benutzerdefinierten Power BI-Visuals](power-bi-custom-visuals-faq.md#organizational-custom-visuals).
