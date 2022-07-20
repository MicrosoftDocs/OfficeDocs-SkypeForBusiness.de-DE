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
description: Erfahren Sie, wie Sie Apps von Drittanbietern über den Teams-Store mithilfe einer Kreditkarte, einer Debitkarte oder über die Rechnungsabrechnung erwerben.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880239"
---
# <a name="purchase-third-party-apps-for-teams"></a>Erwerben von Drittanbieter-Apps für Teams

Teams-Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Dienstabonnements, um die vollständige Funktionalität und den Umfang der App zu nutzen. Diese Dienstabonnements werden als SaaS-Angebote (Software as a Service) bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) erworben werden können.

Auf der Seite ["Apps verwalten](manage-apps.md) " im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Sie können beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen und organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste erwerben, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die Spalte **"Lizenzen** " in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet.

![Screenshot der Seite zum Verwalten von Apps mit Kauflizenzen.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Erwerben von Apps im Teams Admin Center

> [!IMPORTANT]
> Wenn Sie den App-Einkauf aktivieren, wird auch der In-App-Einkauf aktiviert. Benutzern werden möglicherweise In-App-Kaufangebote angezeigt, die vom ISV für ihre App gesteuert werden. Wenn Sie verhindern möchten, dass Ihre Benutzer eine App kaufen, müssen Sie die App blockieren. Weitere Informationen zum Blockieren einer App finden [Sie unter "Verwalten von App-Richtlinien](app-policies.md) ", oder [erfahren Sie, wie Sie eine App auf Organisationsebene blockieren](manage-apps.md#allow-and-block-apps).

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Centers zu **"Teams-Apps** > **[verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.

1. Suchen Sie nach der gewünschten App anhand ihres Namens. Um Apps zu identifizieren, die über ein kostenpflichtiges SaaS-Abonnement verfügen, suchen Sie in der Spalte **"Lizenzen** ". Jede App hat einen der folgenden Werte:
    * **Kauf**: Die App bietet ein SaaS-Abonnement und steht zum Kauf zur Verfügung.  
    * **Gekauft**: Die App bietet ein SaaS-Abonnement an, und Sie haben Lizenzen dafür erworben.
    * **- -**: Die App bietet kein SaaS-Abonnement an.

1. Wenn Sie die App gefunden haben, wählen Sie **"Kaufen** " aus, um auf der Seite mit den App-Details zur Registerkarte **"Pläne und Preise** " zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen benötigen, wählen Sie **"Weitere Informationen"** aus, um zur [App-Seite in AppSource](https://appsource.microsoft.com/) zu wechseln.

   > [!NOTE]
   > Private Pläne können auch zum Kauf aufgeführt werden, einschließlich Sonderpreisen, die Ihre Organisation zuvor mit einem ISV ausgehandelt hat. Diese Pläne weisen die Bezeichnung **"Privater Plan"** unter dem Plannamen auf.

1. Um eine App zu abonnieren, wählen Sie den gewünschten Plan und dann **"Kaufen**" aus. Der Checkout-Fluss wird direkt im Teams Admin Center geöffnet.

1. Wählen Sie die Anzahl der Benutzerlizenzen aus, die Sie kaufen möchten.

1. Überprüfen Sie, ob das Abrechnungskonto und die verkauften Adressen korrekt sind. Wenn Sie noch nicht über eines verfügen, wählen Sie **"Hinzufügen"** aus. Weitere Informationen zu Abrechnungskonten finden [Sie unter "Grundlegendes zu Abrechnungskonten"](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Nur ein globaler Admin kann ein neues Abrechnungskonto hinzufügen.

1. Stellen Sie sicher, dass das richtige Abrechnungsprofil ausgewählt ist. Wenn Sie noch keines haben, wählen Sie **"Neu hinzufügen"** aus. Sie haben die Möglichkeit, mit einer Kreditkarte, einer Debitkarte oder mit [Rechnungsabrechnung](#invoice-billing) zu bezahlen. Mit dem Abrechnungsprofil können Sie auch eine Bestellnummer hinzufügen, um Ihre Bestellung später zu identifizieren. Weitere Informationen zu Abrechnungsprofilen finden [Sie unter Grundlegendes zu Abrechnungsprofilen](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Wählen Sie **"Bestellung aufgeben"** aus.

1. Wählen Sie **"Einrichten** " aus, um Ihr Abonnement auf der Website des Herausgebers zu aktivieren. Wenn Sie Ihr Abonnement nach dem Kauf nicht einrichten, können Sie dies später tun, indem Sie **"Lizenzen verwalten"** auswählen.

Nachdem Sie das SaaS-Angebot erworben haben, das der Teams-App zugeordnet ist, können Sie die folgenden Kaufdetails auf der Registerkarte **"Pläne und Preise** " der App-Detailseite anzeigen.

* **Lizenzaktivierungsdatum**: Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird es als **Abonnement mit ausstehender Aktivierung** angezeigt.
* **Lizenzen**: Anzahl der Lizenzen, die Sie erworben haben.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte &quot;Pläne und Preise&quot; auf der Seite &quot;App-Details&quot; im Teams Admin Center.":::

Um die erworbenen Lizenzen anzuzeigen und zu verwalten, wählen Sie **"Lizenzen verwalten**" aus, um auf die Microsoft 365 Admin Center zuzugreifen.

Globale Administratoren können weitere Lizenzen hinzufügen, Lizenzen entfernen und Abonnements für Einkäufe kündigen, die von jedem in der Organisation getätigt wurden. Teams-Dienstadministratoren können die gleichen Aktionen für selbst getätigte Einkäufe ausführen. Wenn ein Teams-Dienstadministrator jedoch auch über die Rolle "Abrechnungsadministrator" verfügt, kann er Käufe von jedem in der Organisation verwalten.

> [!NOTE]
> Wenn ein globaler Admin ein Abonnement verwalten möchte, das von einem anderen globalen Admin erworben wurde, muss es sich im selben Abrechnungskonto befinden. Sie können einem anderen globalen Admin Zugriff auf ein erworbenes Abonnement gewähren, indem Sie die App im [Microsoft 365 Admin Center](https://admin.microsoft.com) auswählen. Wechseln Sie dort zu **Abrechnungsprofil** >  anzeigen **Abrechnungskonto** >  auswählen **Rollen** >  zuweisen **Weitere globale Administratoren hinzufügen**.

### <a name="invoice-billing"></a>Rechnungsabrechnung

* Die Rechnungsabrechnung ist als Zahlungsoption für einige Transaktionen verfügbar.
* Bei der ersten Verwendung der Rechnungsabrechnung ist eine Bonitätsprüfung erforderlich, die bis zu 24 bis 48 Stunden für die Genehmigung dauern kann. Die Rechnungsabrechnung ist erst verfügbar, wenn die Bonitätsprüfung abgeschlossen ist. Sie können Ihre Bestellung mit einer Kreditkarte aufgeben oder es später erneut versuchen, nachdem Ihre Bonitätsprüfung genehmigt wurde.
* Die Rechnungsabrechnung ist nur für globale Administratoren oder einen Administrator mit den Berechtigungen "Teams-Dienstadministrator" und "Abrechnungsadministrator" verfügbar.
* Die Rechnungsabrechnung ist beim Kauf eines Plans mit einer 30-tägigen kostenlosen Testversion nicht verfügbar.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Auflisten und Verkaufen eines SaaS-Angebots für eine Teams-App

Entwickler können SaaS-Angebote erstellen, die ihren Teams-Apps zugeordnet sind. Diese Angebote werden über [das Partner Center](https://partner.microsoft.com) veröffentlicht und stehen Organisationen zum Kauf über [AppSource](https://appsource.microsoft.com/) und das Microsoft Teams Admin Center zur Verfügung.

Weitere Informationen für App-Entwickler von Drittanbietern finden [Sie unter Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Verwandte Artikel

* [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [In Azure Active Directory integrierte Rollen](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365-Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles)
