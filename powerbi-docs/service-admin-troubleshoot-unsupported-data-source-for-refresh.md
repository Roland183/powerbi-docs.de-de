---
title: Problembehandlung bei nicht unterstützter Datenquelle für die Aktualisierung
description: Problembehandlung bei nicht unterstützter Datenquelle für die Aktualisierung
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 340c3fe2dc18fadb6be0ac47556547e6131833bc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280399"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Problembehandlung bei nicht unterstützter Datenquelle für die Aktualisierung
Bei der Konfiguration eines Datasets für die planmäßige Aktualisierung kann ein Fehler angezeigt werden.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Dies geschieht, wenn die innerhalb von Power BI-Desktop verwendete Datenquelle für die Aktualisierung nicht unterstützt wird. Sie müssen die von Ihnen verwendete Datenquelle suchen und mit der Liste der unterstützten Datenquellen unter [Aktualisieren von Daten in Power BI](refresh-data.md) vergleichen. 

## <a name="find-the-data-source"></a>Suchen der Datenquelle
Wenn Sie unsicher sind, welche Datenquelle verwendet wurde, können Sie diese suchen, indem Sie die folgenden Schritte in Power BI Desktop ausführen.  

1. Vergewissern Sie sich in Power BI Desktop, dass Sie sich im **Berichtsbereich** befinden.  
   ![Power BI Desktop-Berichtsbereich](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Wählen Sie im Menüband die Option **Abfragen bearbeiten** aus.  
   ![Abfragen bearbeiten](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Wählen Sie **Erweiterter Editor**aus.  
   ![Erweiterter Editor](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Notieren Sie sich den für die Datenquelle aufgeführten Anbieter.  In diesem Beispiel ist der Anbieter Active Directory.  
   ![Datenquellenanbieter](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Vergleichen Sie den Anbieter mit der Liste der unterstützten Datenquellen unter [Aktualisieren von Daten in Power BI](refresh-data.md).  Sie werden feststellen, dass Active Directory für die Aktualisierung keine unterstützte Datenquelle ist.  

## <a name="next-steps"></a>Nächste Schritte
[Datenaktualisierung](refresh-data.md)  
[Power BI Gateway – Personal](service-gateway-personal-mode.md)  
[Lokales Datengateway](service-gateway-onprem.md)  
[Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md)  
[Problembehandlung für Power BI Gateway – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

