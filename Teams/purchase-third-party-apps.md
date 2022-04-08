---
title: Erwerben von Drittanbieter-Apps für Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Erfahren Sie, wie Sie Apps von Drittanbietern für Teams im Microsoft Teams Admin Center erwerben.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 84a527fbd8ec59817b4f0d3ee64a970c44d9abd4
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712929"
---
# <a name="purchase-third-party-apps-for-teams"></a>Erwerben von Drittanbieter-Apps für Teams

Teams Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Dienstabonnements, um die volle Funktionalität und den Umfang der App zu nutzen. Diese Dienstabonnements werden als SaaS-Angebote (Software as a Service) bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das Microsoft Teams Admin Center erworben werden können.

Auf der Seite ["Apps verwalten](manage-apps.md)" im Microsoft Teams Admin Center können Sie alle Teams Apps für Ihre Organisation anzeigen und verwalten. Sie können beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen und organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste erwerben, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die Spalte **"Lizenzen** " in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet.

![Screenshot der Seite zum Verwalten von Apps mit Kauflizenzen.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Erwerben von Apps im Teams Admin Center

> [!IMPORTANT]
> Wenn Sie den App-Einkauf aktivieren, wird auch der In-App-Einkauf aktiviert. Benutzern werden möglicherweise In-App-Kaufangebote angezeigt, die vom ISV für ihre App gesteuert werden. Wenn Sie verhindern möchten, dass Ihre Benutzer eine App kaufen, müssen Sie die App blockieren. Weitere Informationen zum Blockieren einer App finden [Sie unter "Verwalten von App-Richtlinien](app-policies.md) ", oder [erfahren Sie, wie Sie eine App auf Organisationsebene blockieren](manage-apps.md#allow-and-block-apps).

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder Teams Dienstadministrator sein, um auf die Seite zugreifen zu können.
1. Suchen Sie nach der gewünschten App. Um Apps zu identifizieren, die über ein kostenpflichtiges SaaS-Abonnement verfügen, suchen Sie in der Spalte **"Lizenzen** ". Jede App hat einen der folgenden Werte:
    - **Kauf**: Die App bietet ein SaaS-Abonnement und steht zum Kauf zur Verfügung.  
    - **Gekauft**: Die App bietet ein SaaS-Abonnement an, und Sie haben Lizenzen dafür erworben.
    - **- -**: Die App bietet kein SaaS-Abonnement an.
1. Wenn Sie die App gefunden haben, klicken Sie auf **"Kaufen** ", um auf der Seite "App-Details" zur Registerkarte " **Pläne und Preise** " zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen benötigen, wählen Sie **"Weitere Informationen"** aus, um zur [App-Seite in AppSource](https://appsource.microsoft.com/) zu wechseln.

   > [!NOTE]
   > Private Pläne können auch zum Kauf aufgeführt werden, einschließlich Sonderpreisen, die Ihre Organisation zuvor mit einem ISV ausgehandelt hat. Diese Pläne weisen die Bezeichnung **"Privater Plan"** unter dem Plannamen auf.

1. Um eine App zu abonnieren, wählen Sie den gewünschten Plan und dann **"Kaufen**" aus. Der Checkout-Fluss wird direkt im Teams Admin Center geöffnet.

1. Wählen Sie die Anzahl der Benutzerlizenzen aus, die Sie kaufen möchten.
1. Überprüfen Sie, ob das Abrechnungskonto und die verkaufte Adresse korrekt sind. Wenn Sie noch nicht über eine verfügen, fügen Sie eine neue hinzu, indem Sie " **Hinzufügen"** auswählen. Weitere Informationen zu Abrechnungskonten finden [Sie unter "Grundlegendes zu Abrechnungskonten"](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Sie müssen ein globaler Administrator sein, um ein neues Abrechnungskonto hinzufügen zu können.

1. Überprüfen Sie, ob das richtige Abrechnungsprofil ausgewählt ist. Wenn Sie noch nicht über eine verfügen, fügen Sie eine neue hinzu, indem Sie " **Neu hinzufügen"** auswählen. Sie haben die Möglichkeit, mit einer Kreditkarte, einer Debitkarte oder mit [Rechnungsabrechnung](#invoice-billing) zu bezahlen. Mit dem Abrechnungsprofil können Sie auch eine Bestellnummer hinzufügen, um Ihre Bestellung später zu identifizieren. Weitere Informationen zu Abrechnungsprofilen finden [Sie unter Grundlegendes zu Abrechnungsprofilen](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
1. Wählen Sie **"Bestellung aufgeben"** aus.
1. Wählen Sie **"Einrichten** " aus, um Ihr Abonnement auf der Website des Herausgebers zu aktivieren. Wenn Sie Ihr Abonnement nach dem Kauf nicht einrichten, können Sie dies später tun, indem Sie **"Lizenzen verwalten"** auswählen.

Nachdem Sie das SaaS-Angebot erworben haben, das der Teams-App zugeordnet ist, können Sie die folgenden Kaufdetails auf der Registerkarte **"Pläne und Preise**" auf der Seite mit den App-Details anzeigen.

- **Lizenzaktivierungsdatum**: Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird dies als **"Abonnement ausstehend"** angezeigt.
- **Lizenzen**: Anzahl der erworbenen Lizenzen.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte &quot;Pläne und Preise&quot; auf der Seite &quot;App-Details&quot;.":::

Wählen Sie **"Lizenzen verwalten**" aus, um zum Microsoft 365 Admin Center zu wechseln, um die erworbenen Lizenzen anzuzeigen und zu verwalten.

Globale Administratoren können weitere Lizenzen hinzufügen, Lizenzen entfernen und Abonnements für Einkäufe kündigen, die von jedem in der Organisation getätigt wurden. Teams Dienstadministratoren können dieselben Aktionen für selbst getätigte Käufe ausführen. Wenn jedoch ein Teams-Dienstadministrator auch über die Rolle "Abrechnungsadministrator" verfügt, kann er Käufe von jedem in der Organisation verwalten.

> [!NOTE]
> Wenn ein globaler Administrator ein Abonnement verwalten möchte, das von einem anderen globalen Administrator erworben wurde, muss er sich im selben Abrechnungskonto befinden. Sie können einem anderen globalen Administrator Zugriff auf ein Abonnement gewähren, das Sie erworben haben, indem Sie die App im Microsoft 365 Admin Center auswählen. Wechseln Sie dort zu **"Abrechnungsprofil** >  **anzeigenAbwählen Abrechnungskonto** >  **Zuweisen von RollenWeitere** >  **globale Administratoren hinzufügen**".

### <a name="invoice-billing"></a>Rechnungsabrechnung

- Die Rechnungsabrechnung ist als Zahlungsoption für einige Transaktionen verfügbar.
- Bei der ersten Verwendung der Rechnungsabrechnung ist eine Bonitätsprüfung erforderlich, die bis zu 24 bis 48 Stunden für die Genehmigung dauern kann. Die Rechnungsabrechnung ist erst verfügbar, wenn die Bonitätsprüfung abgeschlossen ist. Sie können Ihre Bestellung mit einer Kreditkarte aufgeben oder es später erneut versuchen, nachdem Ihre Bonitätsprüfung genehmigt wurde.
- Die Rechnungsabrechnung ist nur für globale Administratoren oder administratoren verfügbar, die sowohl Teams Dienstadministrator- als auch Abrechnungsadministratorberechtigungen besitzen.
- Die Rechnungsabrechnung ist beim Kauf eines Plans mit einer 30-tägigen kostenlosen Testversion nicht verfügbar.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Haben Sie ein SaaS-Angebot für eine Teams-App, die Sie im Microsoft Teams Admin Center und AppSource auflisten und verkaufen möchten?

Entwickler können SaaS-Angebote erstellen, die ihren Teams-Apps zugeordnet sind. Diese Angebote werden über [das Partner Center](https://partner.microsoft.com) veröffentlicht und stehen Organisationen zum Kauf über [AppSource](https://appsource.microsoft.com/) und das Microsoft Teams Admin Center zur Verfügung.

App-Entwickler von Drittanbietern können ein [SaaS-Angebot erstellen](/azure/marketplace/partner-center-portal/create-new-saas-offer) , um weitere Informationen zu erhalten.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD integrierter Rollen](/azure/active-directory/roles/permissions-reference)
- [administratorrollen Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
