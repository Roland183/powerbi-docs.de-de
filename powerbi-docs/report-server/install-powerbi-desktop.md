---
title: Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop
description: Erfahren Sie mehr zum Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/24/2019
ms.openlocfilehash: 7abf679c663f9c71c277c74960fe65c9aee6568d
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "56324965"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop

Erfahren Sie mehr zum Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop.

Damit Sie Power BI-Berichte für Power BI-Berichtsserver erstellen können, müssen Sie die für Power BI-Berichtsserver optimierte Power BI Desktop-Version herunterladen und installieren. Diese Version unterscheidet sich von der Power BI Desktop-Version, die mit dem Power BI-Dienst verwendet wird. Beispielsweise enthält die Power BI Desktop-Version für den Power BI-Dienst Previewfunktionen, die erst nach der Veröffentlichung in der Version für den Power BI-Berichtsserver verfügbar sind. Sie müssen diese Version verwenden, um sicherzustellen, dass der Berichtsserver mit einer bekannten Version der Berichte und des Modells interagieren kann. 

Power BI Desktop und Power BI Desktop (optimiert für den Power BI-Berichtsserver) können glücklicherweise parallel auf dem gleichen Computer installiert werden.

## <a name="download-and-install-power-bi-desktop"></a>Herunterladen und Installieren von Power BI Desktop

Die einfachste Möglichkeit, um sicherzustellen, dass Sie die aktuelle Version des für Power BI-Berichtsserver optimiertem Power BI Desktop verwenden, besteht darin, zunächst das Webportal des Berichtsservers aufzurufen.

1. Wählen Sie im Report Server Web-Portal die **herunterladen** Pfeil > **Power BI Desktop**.

    ![Power BI Desktop aus dem Webportal herunterladen](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Sie können auch direkt zu [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=2055039) (optimiert für Power BI-Berichtsserver – Januar 2019) im Microsoft Download Center navigieren.

2. Wählen Sie im Download Center **Download** aus.

3. Wählen Sie abhängig von Ihrem Computer eine der folgenden Versionen aus: 

    - **PBIDesktopRS.msi** (32-Bit-Version) oder

    - **PBIDesktopRS_x64.msi** (64-Bit-Version).

1. Führen Sie den Setup-Assistenten für Power BI Desktop (Januar 2019) aus, nachdem Sie das Installationsprogramm heruntergeladen haben.

2. Aktivieren Sie am Ende des Installationsvorgangs **Power BI Desktop jetzt starten**.

    Die App wird automatisch gestartet, sodass Sie gleich loslegen können.

## <a name="verify-youre-using-the-correct-version"></a>Überprüfen, ob Sie die richtige Version verwenden
Sie können ganz einfach überprüfen, ob Sie die richtige Power BI Desktop-Version verwenden: Schauen Sie sich den Startbildschirm oder die Titelleiste in Power BI Desktop an. In der Titelleiste werden Monat und Jahr des Releases angegeben. Darüber hinaus sind die Farben des Power BI-Logos umgekehrt, d. h. gelb auf schwarz anstatt schwarz auf gelb.

![Titelleiste für „Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop“](media/install-powerbi-desktop/power-bi-report-server-desktop-jan-2019.png)

Die Power BI Desktop-Version für den Power BI-Dienst gibt Monat und Jahr nicht in der Titelleiste an.

## <a name="file-extension-association"></a>Zuordnung der Dateinamenerweiterung
Wenn Sie Power BI Desktop und Power BI Desktop (optimiert für den Power BI-Berichtsserver) auf demselben Computer installieren, weist die neueste Installation von Power BI Desktop die Dateizuordnung zu PBIX-Dateien auf. Wenn Sie also auf eine PBIX-Datei doppelklicken, wird die Power BI Desktop-Version gestartet, die Sie zuletzt installiert haben.

Wenn Sie Power BI Desktop bereits installiert haben und dann Power BI Desktop (optimiert für den Power BI-Berichtsserver) installieren, werden alle PBIX-Dateien standardmäßig in für den Power BI-Berichtsserver optimiertem Power BI Desktop geöffnet. Wenn Sie möchten, dass beim Öffnen von PBIX-Dateien standardmäßig Power BI Desktop gestartet wird, müssen Sie [Power BI Desktop aus dem Microsoft Store](http://aka.ms/pbidesktopstore) erneut installieren.

Sie können immer zuerst die Version von Power BI Desktop öffnen, die Sie verwenden möchten. Öffnen Sie anschließend die Datei in Power BI Desktop.

Zum Bearbeiten eines Power BI-Berichts auf dem Power BI-Berichtsserver oder Erstellen eines neuen Power BI-Berichts über das Webportal wird stets die richtige Version von Power BI Desktop geöffnet.

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

Power BI-Berichte in Power BI-Berichtsserver und im Power BI-Dienst (http://app.powerbi.com) sowie in den mobilen Power BI-Apps funktionieren fast identisch, wobei sich einige Features aber unterscheiden.

### <a name="in-a-browser"></a>In einem Browser

Power BI-Berichtsserver-Berichte unterstützen alle Visualisierungen, einschließlich:

* Benutzerdefinierte Visualisierungen

Power BI-Berichtsserver-Berichte unterstützen Folgendes nicht:

* Visuelle R-Elemente
* ArcGIS-Karten
* Brotkrümel
* Vorschaufeatures für Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>In den mobilen Power BI-Apps

Power BI-Berichtsserver-Berichte unterstützen alle Grundfunktionen in den [mobilen Power BI-Apps](../consumer/mobile/mobile-apps-for-mobile-devices.md), einschließlich:

* [Berichtslayout für Smartphones](../desktop-create-phone-report.md): Sie können einen Bericht für die Power BI Mobile-Apps optimieren. Auf dem Mobiltelefon sind optimierte Berichte mit einem speziellen Symbol, ![Berichtslayout für Smartphones](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png), gekennzeichnet, und sie weisen ein besonderes Layout auf.
  
    ![Für Telefone optimierter Bericht](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Die folgenden Funktionen werden von den Power BI-Berichtsserver-Berichten in den mobilen Power BI-Apps nicht unterstützt:

* Visuelle R-Elemente
* ArcGIS-Karten
* Benutzerdefinierte Visualisierungen
* Brotkrümel
* Geofilter oder Strichcodes

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop für frühere Versionen von Power BI-Berichtsserver

Wenn Sie eine frühere Version des Berichtsservers verwenden, benötigen Sie die entsprechende Version von Power BI Desktop. Hier ist die vorherige Version.

- Microsoft Power BI Desktop ([optimiert für den Power BI-Berichtsserver, August 2018](https://www.microsoft.com/download/details.aspx?id=57271))

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Power BI Desktop installiert haben, können Sie mit dem Erstellen von Power BI-Berichten beginnen.

[Erstellen eines Power BI-Berichts für Power BI-Berichtsserver](quickstart-create-powerbi-report.md)  
[Was ist der Power BI-Berichtsserver?](get-started.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
