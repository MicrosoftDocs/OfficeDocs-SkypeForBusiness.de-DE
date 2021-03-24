---
title: Verbinden der Patienten-App mit Azure API for FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Erfahren Sie, wie Sie die Patienten-App in Microsoft Teams mit der Azure-API für FHIR (Fast Healthcare Interoperability Resources) verbinden.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096267"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Verbinden der Patienten-App mit Azure API for FHIR

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Führen Sie die folgenden Schritte aus, um der Patienten-App in Microsoft Teams den Zugriff auf eine Azure-API für FHIR-Instanz zu ermöglichen. In diesem Artikel wird davon ausgegangen, dass Sie eine [Azure-API für FHIR-Instanz](https://azure.microsoft.com/services/azure-api-for-fhir/) in Ihrem Mandanten eingerichtet und konfiguriert haben.  Wenn Sie noch keine Azure API für FHIR-Instanz in Ihrem Mandanten erstellt haben, lesen Sie Schnellstart: Bereitstellen der [Azure-API für FHIR mithilfe des Azure-Portals.](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. Klicken [Sie hier,](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) um die Zustimmung des Administrator für die Patienten-App zu erteilen. Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Mandantenadministrator- oder globalen Administratoranmeldeinformationen an, und klicken Sie dann auf Annehmen, **um** die erforderlichen Berechtigungen zu erteilen.

    ![Screenshot der Berechtigungsanfrage für die Patienten-App](../../media/patients-app-permissions-request.png)

    Nachdem Sie dies akzeptiert haben, schließen Sie das Fenster. Es wird eine Seite angezeigt, die wie dies aussehen kann. Sie können die Fehlermeldung auf der Seite ignorieren. Sie ist harmlos und weist darauf hin, dass die Zustimmung erteilt wird. (Wir arbeiten an einer benutzerfreundlicheren Seite für diese URL. Bleiben Sie dran!)

    ![Screenshot der Berechtigungsanfrage für die Patienten-App](../../media/patients-app-permissions-request-granted.png)

2. Melden Sie sich mit Ihren [Administratoranmeldeinformationen](https://portal.azure.com) beim Azure-Portal an.

3. Wählen Sie im linken Navigationsbereich **Azure Active Directory** und dann **Enterprise-Anwendungen aus.**

    Suchen Sie nach einer Zeile mit dem Namen **Patienten (dev),** und kopieren Sie dann den Wert in der Spalte **Objekt-ID** in die Zwischenablage.

    ![Screenshot der Zeile Patienten (Dev) im Azure-Portal](../../media/patients-app-azure-portal-object-id.png)

4. Wechseln Sie zur Azure-API für FHIR-Ressourceninstanz, mit der Sie die Patienten-App verbinden möchten (indem Sie danach suchen oder ihre Ressourcen durchsuchen), und öffnen Sie dann die Einstellungen für diese Instanz.

    ![Screenshot der Azure-API für FHIR-Instanzeinstellungen im Azure-Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Klicken **Sie auf Authentifizierung,** und fügen Sie dann die Objekt-ID, die Sie in Schritt 3 kopiert haben, in das Feld Zulässige **Objekt-IDs** ein. Dadurch kann die Patienten-App auf den FHIR-Server zugreifen. Nachdem Sie die Objekt-ID eingefügt haben, überprüft Azure Active Directory sie, und daneben wird ein grünes Häkchen angezeigt.

    ![Screenshot der Authentifizierungseinstellungen im Azure-Portal](../../media/patients-app-azure-portal-authentication.png)

6. Klicken Sie auf **Speichern**. Dadurch wird die -Instanz erneut bereitstellen, was einige Minuten dauern kann.

7. Klicken Sie **auf Übersicht,** und kopieren Sie dann die URL aus **dem FHIR-Metadatenendpunkt.** Entfernen Sie das Metadatentag, um die FHIR-Server-URL zu erhalten. Beispiel: `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![Der Metadatenendpunkt im Azure-Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Wechseln Sie in Teams zu der In Ihr Team geladenen Patienten-App-Instanz, klicken Sie auf **Einstellungen,** und geben Sie dann im Feld Link die URL für den FHIR-Serverendpunkt ein.  Klicken Sie dann auf **Verbinden,** um eine Verbindung herzustellen und Patienten zu Ihrer Liste hinzuzufügen.  

    ![ Einstellungen der Patienten-App in Teams](../../media/patients-app-teams.png)

    Wenn während dieses Schritts beim Herstellen einer Verbindung mit Teams eine Fehlermeldung angezeigt wird, senden Sie einen detaillierten Screenshot des Fehlers, Protokolle von [Fiddler](https://www.telerik.com/download/fiddler) und alle anderen Schritte zumPropro in einer E-Mail mit der Betreffzeile "Patienten-App – EMR-Modus– Problembehandlung" an [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht der Patienten-App](patients-app-overview.md)
- [Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)