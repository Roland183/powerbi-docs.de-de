---
title: Übertragen von Daten in ein Dataset per Push
description: Übertragen von Daten in ein Power BI-Dataset per Push
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 642a8e7dd118838b5ea12c8758841ee44a8e6595
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762258"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Übertragen von Daten in ein Power BI-Dataset per Push

Mit der Power BI-API können Sie Daten per Push in ein Power BI-Dataset übertragen. Angenommen, Sie möchten einen vorhandenen Geschäftsworkflow erweitern, um wichtige Daten per Push in ein Dataset zu übertragen. In diesem Fall möchten Sie das Dataset „Sales Marketing“ mit einer Tabelle „Product“ per Push in ein Dataset übertragen.

Damit Sie Daten per Push an ein Dataset übermitteln können, benötigen Sie ein Azure Active Directory (Azure AD)- und ein [Power BI-Konto](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Schritte zum Übertragen von Daten per Push in ein Dataset

* Schritt 1: [Registrieren einer App in Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Schritt 2: [Abrufen eines Authentifizierungszugriffstokens](walkthrough-push-data-get-token.md)
* Schritt 3: [Erstellen eines Datasets in Power BI](walkthrough-push-data-create-dataset.md)
* Schritt 4: [Abrufen eines Datasets, um einer Power BI-Tabelle Zeilen hinzuzufügen](walkthrough-push-data-get-datasets.md)
* Schritt 5: [Hinzufügen von Zeilen zu einer Power BI-Tabelle](walkthrough-push-data-add-rows.md)

Im nächste Abschnitt folgt eine allgemeine Erläuterung von Power BI-API-Vorgängen, die Daten per Push übertragen.

## <a name="power-bi-api-operations-to-push-data"></a>Power BI-API-Vorgänge zum Übertragen von Daten per Push

Mit der Power BI-REST-API können Sie Datenquellen per Push in Power BI übertragen. Wenn eine Anwendung einem Dataset Zeilen hinzufügt, werden die Kacheln auf dem Dashboard automatisch mit den neuen Daten aktualisiert. Verwenden Sie den Vorgang [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) mit dem Vorgang [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows), um Daten per Push zu übertragen. Zum Auffinden eines Datasets verwenden Sie den Vorgang [Datasets abrufen](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets). Für alle diese Vorgänge können Sie eine Gruppen-ID übergeben, um mit einer Gruppe zu arbeiten. Verwenden Sie den Vorgang [Gruppen abrufen](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups), um eine Liste mit Gruppen-IDs abzurufen.

Es folgen die Vorgänge, um Daten per Push in ein Dataset zu übertragen:

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Get Datasets (Datasets abrufen)](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Get Groups (Gruppen abrufen)](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

Erstellen Sie ein Dataset in Power BI durch Übergeben einer JSON-Zeichenfolge (JavaScript Object Notation) an den Power BI-Dienst. Weitere Informationen zu JSON finden Sie unter [Einführung in JSON](http://json.org/).

Die JSON-Zeichenfolge für ein Dataset hat das folgende Format:

**JSON-Objekt mit dem Power BI-Dataset**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Bei unserem Beispiel mit dem Dataset „Sales Marketing“ übergeben Sie eine JSON-Zeichenfolge wie im nachstehenden Beispiel. In diesem Beispiel ist **SalesMarketing** der Name des Datasets und **Product** der Name der Tabelle. Nach Definieren der Tabelle definieren Sie das Tabellenschema. Das Tabellenschema des Datasets **SalesMarketing** weist die folgenden Spalten auf: ProductID, Manufacturer, Category, Segment, Product, IsCompete.

**Beispiel-JSON für Datasetobjekt**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Für ein Power BI-Tabellenschema können Sie die folgenden Datentypen verwenden.

## <a name="power-bi-table-data-types"></a>Power BI-Tabellendatentypen

| **Datentyp** | **Einschränkungen** |
| --- | --- |
| Int64 |Int64.MaxValue und Int64.MinValue sind nicht zulässig. |
| Double |Die Werte Double.MaxValue und Double.MinValue sind nicht zulässig. NaN wird nicht unterstützt. +Infinity und -Infinity werden bei einigen Funktionen (z. B. Min, Max) nicht unterstützt. |
| Boolesch |Keine |
| Datetime |Beim Laden von Daten werden Werte mit Bruchteilen von Tagen auf ganze Vielfache von 1/300 Sekunden (3,33 ms) quantisiert. |
| Zeichenfolge |Derzeit sind bis zu 128.000 Zeichen zulässig. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Weitere Informationen zum Übertragen von Daten per Push in Power BI

Informationen zum Einstieg in das Übertragen von Daten per Push in ein Dataset finden Sie links im Navigationsbereich unter [Schritt 1: Registrieren einer App in Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).

[Nächster Schritt >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Nächste Schritte

[Registrieren bei Power BI](create-an-azure-active-directory-tenant.md)  
[Einführung in JSON](http://json.org/)  
[Übersicht über Power BI-REST-API](overview-of-power-bi-rest-api.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)