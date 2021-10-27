---
title: Erwerben von Drittanbieter-Apps für Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Informationen zum Erwerben von Drittanbieter-Apps für Teams Sie im Microsoft Teams Admin Center.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 19403d35ad2e7263ad6f0d5a2c7a2b22d4249664
ms.sourcegitcommit: c7a6079c9592c28d8b082ff92004ae4706cea76e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2021
ms.locfileid: "60600219"
---
# <a name="purchase-third-party-apps-for-teams"></a>Erwerben von Drittanbieter-Apps für Teams

Teams-Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Serviceabonnements, um den vollen Funktionsumfang und Umfang der App zu nutzen. Diese Dienstabonnements werden als SaaS-Angebote (Software as a Service) bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das Microsoft Teams Admin Center erhältlich sind.

Auf [der Seite Apps](manage-apps.md) verwalten im Microsoft Teams Admin Center können Sie alle Apps Teams Ihrer Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste kaufen, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die **Spalte Lizenzen** in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet.

![Screenshot der Seite "Apps verwalten" für Lizenzen](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Kaufen von Apps im Teams Admin Center

> [!IMPORTANT]
> Wenn Sie ihren Benutzern den Kauf einer App über den Teams-App-Store sperren möchten, müssen Sie die App blockieren. Weitere Informationen zum Blockieren einer App finden Sie unter Verwalten von [App-Richtlinien](app-policies.md) oder Informationen zum Blockieren einer App [auf Organisationsebene.](manage-apps.md#allow-and-block-apps)

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder ein dienstadministrator Teams sein, um auf die Seite zugreifen zu können.
2. Suchen Sie nach der App, die Sie verwenden möchten. Um Apps mit einem kostenpflichtigen SaaS-Abonnement zu identifizieren, sehen Sie in der Spalte **Lizenzen** nach. Jede App hat einen der folgenden Werte:
    - **Kaufen:** Die App bietet ein SaaS-Abonnement und kann zum Kauf angeboten werden.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **- –**: Die App bietet kein SaaS-Abonnement an.
3. Wenn Sie die App finden, klicken  **Sie** auf Kaufen, um auf der Seite mit den App-Details zur Registerkarte Pläne und Preise zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen benötigen, wählen Sie Weitere Informationen **aus,** um zur App-Seite in [AppSource zu wechseln.](https://appsource.microsoft.com/)

> [!NOTE]
> Private Pläne können ebenfalls zum Kauf aufgeführt werden, z. B. Sonderpreise, die Ihre Organisation zuvor mit einem ISV ausgehandelt hat. Diese Pläne haben die Bezeichnung **Privater Plan** unter dem Plannamen.

4. Wenn Sie eine App abonnieren möchten, wählen Sie den plan und dann Kaufen **aus.** Der Auscheckvorgang wird direkt im Teams Admin Center geöffnet.
5. Wählen Sie die Anzahl der Benutzerlizenzen aus, die Sie kaufen möchten.
6. Überprüfen Sie, ob das Abrechnungskonto und die verkaufte Adresse korrekt sind. Wenn Sie noch kein Konto haben, fügen Sie ein neues hinzu, indem Sie **Hinzufügen auswählen.** Weitere Informationen zu Abrechnungskonten finden Sie unter [Verstehen von Abrechnungskonten.](/microsoft-365/commerce/manage-billing-accounts)

> [!NOTE]
> Sie müssen ein globaler Administrator sein, um ein neues Abrechnungskonto hinzufügen zu können.

7. Überprüfen Sie, ob das richtige Abrechnungsprofil ausgewählt ist. Wenn Sie noch kein Konto haben, fügen Sie ein neues hinzu, indem Sie **Neue hinzufügen auswählen.** Sie haben die Möglichkeit, mit einer Kreditkarte, DEBIT-Karte oder per Rechnung [zu bezahlen.](#invoice-billing) Über das Abrechnungsprofil können Sie auch eine Bestellnummer hinzufügen, um Ihre Bestellung später zu identifizieren. Weitere Informationen zu Abrechnungsprofilen finden Sie unter [Verstehen von Abrechnungsprofilen.](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)
8. Wählen **Sie Bestellung bestellen aus.**
9. Wählen **Sie Einrichten aus,** um Ihr Abonnement auf der Website des Herausgebers zu aktivieren. Wenn Sie Ihr Abonnement nach Ihrem Kauf nicht einrichten, können Sie dies später tun, indem Sie **Lizenzen verwalten auswählen.**

Nachdem Sie das SaaS-Angebot erworben haben, das der Teams-App zugeordnet ist, können Sie auf der Seite mit den App-Details auf der Registerkarte Pläne und Preise die folgenden Kaufdetails anzeigen. 

- **Datum der Lizenzaktivierung:** Das Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird dies als **Abonnement aktivierung ausstehend angezeigt.**
- **Lizenzen:** Anzahl der erworbenen Lizenzen.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte "Pläne und Preise" auf der Seite "App-Details".":::

Wählen **Sie Lizenzen verwalten** aus, um zu den Microsoft 365 Admin Center, um die erworbenen Lizenzen anzeigen und zu verwalten.

Globale Administratoren können weitere Lizenzen hinzufügen, Lizenzen entfernen und Abonnements für Einkäufe von allen Personen in der Organisation stornieren. Teams Dienstadministratoren können für Käufe von sich selbst dieselben Aktionen ausführen. Wenn ein Teams Dienstadministrator aber auch über die Rolle des Abrechnungsadministrators verfügt, kann er Einkäufe von allen Personen in der Organisation verwalten.

> [!NOTE]
> Wenn ein globaler Administrator ein Abonnement verwalten möchte, das von einem anderen globalen Administrator erworben wurde, muss er sich im gleichen Abrechnungskonto anmelden. Sie können einem anderen globalen Administrator Zugriff auf ein erworbenes Abonnement geben, indem Sie die App im Microsoft 365 Admin Center. Wechseln Sie von dort aus zu **Abrechnungsprofil anzeigen** Abrechnungskonto auswählen: Rollen  >    >    >  **zuweisen: Weitere globale Administratoren hinzufügen.**

### <a name="invoice-billing"></a>Rechnungsabrechnung

- Für einige Transaktionen ist die Rechnungsabrechnung als Zahlungsoption verfügbar.
- Bei der ersten Verwendung der Rechnungsabrechnung ist eine Bonitätsüberprüfung erforderlich, was bis zu 24 bis 48 Stunden für die Genehmigung dauern kann. Die Rechnungsabrechnung ist erst nach Abschluss der Bonitätsprüfung verfügbar. Sie können Ihre Bestellung mit Kreditkarte bestellen oder es später erneut versuchen, nachdem Ihre Kreditwürdigkeitsüberprüfung genehmigt wurde.
- Rechnungsabrechnung ist nur für globale Administratoren oder einen Administrator mit Teams Dienstadministrator- und Abrechnungsadministratorberechtigungen verfügbar.
- Rechnungsabrechnung ist nicht verfügbar, wenn Sie einen Plan mit einer kostenlosen Testversion von 30 Tage erwerben.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Haben Sie ein SaaS-Angebot für Teams-App, die Sie im Microsoft Teams Admin Center und appSource anbieten und verkaufen möchten?

Entwickler können SaaS-Angebote erstellen, die ihren Apps Teams sind. Diese Angebote werden über [Partner Center veröffentlicht](https://partner.microsoft.com) und stehen Organisationen zum Kauf über [AppSource](https://appsource.microsoft.com/) und Microsoft Teams Admin Center zur Verfügung.

App-Entwickler von Drittanbietern finden weitere Informationen unter Erstellen [eines SaaS-Angebots.](/azure/marketplace/partner-center-portal/create-new-saas-offer)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD integrierte Rollen](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles)