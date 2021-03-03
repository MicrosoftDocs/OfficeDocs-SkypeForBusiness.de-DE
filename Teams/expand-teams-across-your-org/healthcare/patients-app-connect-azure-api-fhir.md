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
description: Hier erfahren Sie, wie Sie die Patienten-app in Microsoft Teams mit Azure-API für FHIR (fast Healthcare-Interoperabilitäts Ressourcen) verbinden.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731153"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Verbinden der Patienten-App mit Azure API for FHIR

> [!NOTE]
> Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt. Alle Daten, die mit der Patienten-App verknüpft sind, werden in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden. Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.
>
>Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen. Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen. Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Führen Sie die folgenden Schritte aus, um der Patienten-app in Microsoft Teams den Zugriff auf eine Azure-API für die FHIR-Instanz zu ermöglichen. In diesem Artikel wird davon ausgegangen, dass Sie eine [Azure-API für die FHIR-Instanz](https://azure.microsoft.com/services/azure-api-for-fhir/) eingerichtet und in Ihrem Mandanten konfiguriert haben.  Wenn Sie noch keine Azure-API für die FHIR-Instanz in Ihrem Mandanten erstellt haben, lesen Sie [Schnellstart: Bereitstellen der Azure-API für FHIR mithilfe von Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).

1. Klicken Sie [hier](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) , um die Zustimmung des Administrators für die Patienten-APP zu erteilen. Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem mandantenadministrator oder den globalen Administratoranmeldeinformationen an, und klicken Sie dann auf **annehmen** , um die erforderlichen Berechtigungen zu erteilen.

    ![Screenshot der Berechtigungsanforderung für die Patienten-App](../../media/patients-app-permissions-request.png)

    Nachdem Sie die Ansicht akzeptiert haben, schließen Sie das Fenster. Es wird eine Seite angezeigt, die wie folgt aussehen kann. Sie können die Fehlermeldung auf der Seite ignorieren. Sie ist harmlos und gibt an, dass die Zustimmung gewährt wird. (Wir arbeiten an einer benutzerfreundlicheren Seite für diese URL. Bleiben Sie dran!)

    ![Screenshot der App "Berechtigungsanforderung für Patienten"](../../media/patients-app-permissions-request-granted.png)

2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Azure-Portal](https://portal.azure.com) an.

3. Wählen Sie in der linken Navigationsleiste **Azure Active Directory** aus, und wählen Sie dann **Enterprise-Anwendungen** aus.

    Suchen Sie nach einer Zeile mit dem Namen **patients (dev)**, und kopieren Sie dann den Wert in der Spalte **Objekt-ID** in Ihre Zwischenablage.

    ![Screenshot der Zeile "Patienten (dev)" im Azure-Portal](../../media/patients-app-azure-portal-object-id.png)

4. Wechseln Sie zur Azure-API für FHIR-Ressourceninstanz, mit der Sie die Patienten-App verbinden möchten (entweder durchsuchen oder durch Durchsuchen Ihrer Ressourcen), und öffnen Sie dann die Einstellungen für diese Instanz.

    ![Screenshot der Azure-API für FHIR-Instanzen Einstellungen in Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Klicken Sie auf **Authentifizierung**, und fügen Sie dann die Objekt-ID, die Sie in Schritt 3 kopiert haben, in das Feld **zugelassene Objekt-IDs** ein. Dadurch kann die Patienten-App auf den FHIR-Server zugreifen. Nachdem Sie die Objekt-ID eingefügt haben, wird Sie von Azure Active Directory überprüft, und daneben wird ein grünes Häkchen angezeigt.

    ![Screenshot der Authentifizierungseinstellungen in Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. Klicken Sie auf **Speichern**. Dadurch wird die Instanz erneut bereitgestellt, was einige Minuten dauern kann.

7. Klicken Sie auf **Übersicht**, und kopieren Sie dann die URL aus **FHIR-metadatenpunkt**. Entfernen Sie das Metadata-Tag, um die FHIR-Server-URL abzurufen. Beispiel: `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![der Endpunkt für Metadaten im Azure-Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Wechseln Sie in Teams zur Instanz der Patienten-APP, die in Ihrem Team geladen ist, klicken Sie auf **Einstellungen**, und geben Sie dann im Feld **Link** die URL des FHIR-Servers ein. Klicken Sie dann auf **verbinden** , um eine Verbindung herzustellen, und suchen und Hinzufügen von Patienten zu Ihrer Liste.  

    ![ Einstellungen für Patienten-apps in Teams](../../media/patients-app-teams.png)

    Wenn beim Herstellen einer Verbindung mit Teams während dieses Schritts eine Fehlermeldung angezeigt wird, senden Sie einen detaillierten Screenshot des Fehlers, Protokolle von [Fiddler](https://www.telerik.com/download/fiddler) und alle anderen Repro Schritte in einer e-Mail mit einer Betreffzeile der Problembehandlung "Patienten-App – EMR-Modus" zu [teamsforhealthcare@Service.Microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht der Patienten-App](patients-app-overview.md)
- [Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)
