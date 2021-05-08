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
description: Erfahren Sie, wie Sie die Patienten-App in Microsoft Teams Azure-API für FSERIE (Fast Interoperability Resources im Gesundheitswesen) verbinden.
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

Führen Sie die folgenden Schritte aus, um der Patienten-App in Microsoft Teams Zugriff auf eine Azure-API für F PATIENT-Instanz zu ermöglichen. In diesem Artikel wird davon ausgegangen, dass Sie eine [Azure-API](https://azure.microsoft.com/services/azure-api-for-fhir/) für F IMMER-Instanz in Ihrem Mandanten eingerichtet und konfiguriert haben.  Wenn Sie noch keine Azure-API für FSCHI-Instanz in Ihrem Mandanten erstellt haben, lesen Sie Schnellstart: Bereitstellen der Azure-API für F IMMER mithilfe des [Azure-Portals.](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. Klicken Sie [hier,](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) um die Zustimmung des Administrator für die Patienten-App zu erteilen. Melden Sie sich bei der entsprechenden Aufforderung mit Ihren Anmeldeinformationen als Mandantenadministrator oder globaler Administrator an, und klicken Sie dann auf Annehmen, **um** die erforderlichen Berechtigungen zu erteilen.

    ![Screenshot der Berechtigungsanforderung für die Patienten-App](../../media/patients-app-permissions-request.png)

    Schließen Sie das Fenster, nachdem Sie die Einladung akzeptiert haben. Es wird eine Seite angezeigt, die möglicherweise so aussieht. Sie können die Fehlermeldung auf der Seite ignorieren. Sie ist harmlos und gibt an, dass die Zustimmung erteilt wurde. (Wir arbeiten an einer benutzerfreundlicheren Seite für diese URL. Bleiben Sie dran!)

    ![Screenshot der Berechtigungsanforderung für die Patienten-App](../../media/patients-app-permissions-request-granted.png)

2. Melden Sie sich mit Ihren [Administratoranmeldeinformationen](https://portal.azure.com) beim Azure-Portal an.

3. Wählen Sie im linken Navigationsbereich **Azure Active Directory** aus, und wählen Sie dann Anwendungen **Enterprise aus.**

    Suchen Sie nach einer Zeile namens **Patienten (Entwicklung),** und kopieren Sie dann den Wert in der Spalte **Objekt-ID** in die Zwischenablage.

    ![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)

4. Wechseln Sie zu der Azure-API für FSOURCE-Ressourceninstanz, mit der Sie die Patienten-App verbinden möchten (indem Sie danach suchen oder Ihre Ressourcen durchsuchen), und öffnen Sie dann die Einstellungen für diese Instanz.

    ![Screenshot der Azure-API für FSCHI-Instanzeinstellungen im Azure-Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Klicken **Sie auf Authentifizierung,** und fügen Sie dann die objekt-ID, die Sie in Schritt 3 kopiert haben, in das Feld **Zugelassene Objekt-IDs** ein. Dadurch kann die Patienten-App auf den FSCHI-Server zugreifen. Nachdem Sie die Objekt-ID eingefügt haben, Azure Active Directory sie überprüft, und daneben wird ein grünes Häkchen angezeigt.

    ![Screenshot der Authentifizierungseinstellungen im Azure-Portal](../../media/patients-app-azure-portal-authentication.png)

6. Klicken Sie auf **Speichern**. Dadurch wird die -Instanz erneut bereitstellen, was einige Minuten dauern kann.

7. Klicken **Sie auf Übersicht**, und kopieren Sie dann die URL vom **FSCHI-Metadatenendpunkt**. Entfernen Sie das Metadatentag, um die FSCHI-Server-URL zu erhalten. Beispiel: `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![Der Metadatenendpunkt im Azure-Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Wechseln Teams zu der Patienten-App-Instanz, die in Ihr Team geladen wird, klicken Sie auf **Einstellungen**, und geben Sie dann im Feld **Link** die URL des F UNF-Serverendpunkts ein. Klicken Sie dann auf **Verbinden,** um eine Verbindung herzustellen und zu suchen und Patienten zu Ihrer Liste hinzuzufügen.  

    ![ Patienten-App-Einstellungen in Teams](../../media/patients-app-teams.png)

    Wenn Sie während dieses Schritts beim Herstellen einer Verbindung mit Teams eine Fehlermeldung erhalten, senden Sie einen detaillierten Screenshot des Fehlers, Protokolle von [Fiddler](https://www.telerik.com/download/fiddler) und alle anderen Schritte zur Erneutprozeite in einer E-Mail mit der Betreffzeile "Patienten-App – Behandlung im EMR-Modus" an [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht der Patienten-App](patients-app-overview.md)
- [Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)