---
title: Kaufen von Drittanbieter-Apps für Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Erfahren Sie, wie Sie Apps von Drittanbietern im Teams Store mithilfe einer Kreditkarte, einer Debitkarte oder per Rechnungsstellung kaufen können.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5c3137815ea8e4d02ac987ec0a2b0e50c32c3fcb
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837405"
---
# <a name="purchase-third-party-apps-for-teams"></a>Kaufen von Drittanbieter-Apps für Teams

Teams-Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Dienstabonnements, um die vollständige Funktionalität und den Umfang der App zu erfahren. Diese Dienstabonnements werden als Software-as-a-Service (SaaS)-Angebote bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) für den Kauf verfügbar sind.

Auf der Seite [Apps verwalten](manage-apps.md) im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Beispielsweise können Sie den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen und organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste erwerben, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die Spalte **Lizenzen** in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet. Endbenutzer können Apps mit einer Kreditkarte, einer Debitkarte oder mit Rechnungsabrechnung erwerben.

![Screenshot der Seite „Apps verwalten“ zum Kauf von Lizenzen.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Kauf von Apps im Teams Admin Center

Führen Sie die folgenden Schritte aus, um Apps im Teams Admin Center zu kaufen:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.

1. Suchen Sie anhand des Namens nach der von Ihnen gewünschten App. Um Apps zu identifizieren, die ein kostenpflichtiges SaaS-Abonnement aufweisen, schauen Sie in der Spalte **Lizenzen** nach. Jede App hat einen der folgenden Werte:
    * **Kaufen**: Die App bietet ein SaaS-Abonnement und kann erworben werden.  
    * **Erworben**: Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    * **- -**: Die App bietet kein SaaS-Abonnement.

1. Wenn Sie die App gefunden haben, wählen Sie **Kaufen** aus, um zur Registerkarte **Pläne und Preise** der Detailseite der App zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen benötigen, wählen Sie **Weitere Informationen** aus, um zur Seite der App auf [AppSource](https://appsource.microsoft.com/) zu wechseln.

   > [!NOTE]
   > Private Pläne können auch zum Kauf angeboten werden, die Sonderpreise umfassen, die Ihre Organisation zuvor mit einem ISV ausgehandelt hat. Diese Pläne weisen die Bezeichnung **Privater Plan** unter dem Plannamen auf.

1. Um eine App zu abonnieren, wählen Sie den von Ihnen gewünschten Plan und dann **Kaufen** aus. Der Fluss für den Auftragsabschluss wird direkt im Microsoft Teams Admin Center geöffnet.

1. Wählen Sie die Anzahl der Benutzerlizenzen aus, die Sie kaufen möchten.

1. Bestätigen Sie, dass das Abrechnungskonto und die Käuferadresse korrekt sind. Wenn Sie noch keines besitzen, wählen Sie **Hinzufügen** aus. Weitere Informationen zu Abrechnungskonten finden Sie unter [Verstehen von Abrechnungskonten](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Nur ein globaler Administrator kann ein neues Abrechnungskonto hinzufügen.

1. Bestätigen Sie, dass das richtige Abrechnungsprofil ausgewählt ist. Wenn Sie noch keins haben, wählen Sie **Neu hinzufügen** aus. Sie haben die Möglichkeit, mit einer Kreditkarte, Debitkarte oder mit [Rechnungsstellung](#invoice-billing) zu bezahlen. Mit dem Abrechnungsprofil können Sie auch eine Bestellnummer hinzufügen, um Ihren Auftrag später zu identifizieren. Weitere Informationen zu Abrechnungsprofilen finden Sie unter [Verstehen von Abrechnungsprofilen](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Wählen Sie **Bestellung aufgeben** aus.

1. Wählen Sie **Einrichten** aus, um Ihr Abonnement auf der App-Website des Entwicklers zu aktivieren. Wenn Sie Ihr Abonnement nach dem Kauf nicht einrichten, können Sie dies später tun, indem Sie **Lizenzen verwalten** auswählen.

Nachdem Sie das der Teams-App zugeordnete SaaS-Angebot erworben haben, können Sie die folgenden Kaufdetails auf der Registerkarte **Pläne und Preise** auf der Detailseite der App anzeigen.

* **Lizenzaktivierungsdatum**: Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird es als **Abonnements mit ausstehender Aktivierung** angezeigt.
* **Lizenzen**: Anzahl der Lizenzen, die Sie erworbenen haben.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte „Pläne und Preise“ auf der Detailseite der App im Teams Admin Center.":::

Um die von Ihnen erworbenen Lizenzen anzuzeigen und zu verwalten, wählen Sie **Lizenzen verwalten** aus, um auf das Microsoft 365 Admin Center zuzugreifen.

Globale Administratoren können weitere Lizenzen hinzufügen, Lizenzen entfernen und Abonnements für Käufe kündigen, die von beliebigen Personen in der Organisation getätigt wurden. Teams-Dienstadministratoren können die gleichen Aktionen für Käufe ausführen, die sie selbst getätigt haben. Wenn ein Teams-Dienstadministrator jedoch auch über die Rolle „Abrechnungsadministrator“ verfügt, kann er Käufe verwalten, die von beliebigen Personen in der Organisation getätigt wurden.

> [!NOTE]
> Wenn ein globaler Administrator ein Abonnement verwalten möchte, das von einem anderen globalen Administrator erworben wurde, müssen sie beide im selben Abrechnungskonto befinden. Sie können einem anderen globalen Administrator Zugriff auf ein Abonnement gewähren, das Sie erworben haben, indem Sie die App im [Microsoft 365 Admin Center](https://admin.microsoft.com) auswählen. Greifen Sie im Admin Center auf **Abrechnungsprofil anzeigen** > **Abrechnungskonto auswählen** > **Rollen zuweisen** > **Andere globale Administratoren hinzufügen zu**.

> [!IMPORTANT]
> Wenn Sie den App-Kauf aktivieren, wird auch der In-App-Kauf aktiviert. Benutzern werden möglicherweise In-App-Kaufangebote angezeigt, die vom App-Entwickler für ihre App gesteuert werden. Um zu verhindern, dass Benutzer eine App kaufen, müssen Sie die App blockieren.

### <a name="invoice-billing"></a>Rechnungsstellung

* Die Rechnungsstellung ist für einige Transaktionen als Zahlungsoption verfügbar.
* Für die erste Rechnungsstellung ist eine Bonitätsprüfung erforderlich. Die Genehmigung kann zwischen 24 und 48 Stunden dauern. Die Rechnungsstellung ist erst verfügbar, wenn die Bonitätsprüfung abgeschlossen ist. Sie können Ihre Bestellung mit einer Kreditkarte aufgeben oder es später erneut versuchen, nachdem Ihre Kreditprüfung genehmigt wurde.
* Die Rechnungsstellung ist nur für globale Administratoren oder einen Administrator verfügbar, der sowohl Berechtigungen als Teams-Dienstadministrator wie auch Abrechnungsadministrator besitzt.
* Die Rechnungsstellung ist nicht verfügbar, wenn Sie einen Plan mit einer 30-tägigen kostenlosen Testversion erwerben.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Auflisten und Verkaufen eines SaaS-Angebots für eine Teams-App

Entwickler können SaaS-Angebote erstellen, die ihren Teams-Apps zugeordnet sind. Diese Angebote werden über [Partner Center](https://partner.microsoft.com) veröffentlicht und stehen Organisationen über [AppSource](https://appsource.microsoft.com/) und das Microsoft Teams Admin Center zur Verfügung.

Weitere Informationen für Drittanbieter-App-Entwickler finden Sie unter [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Verwandte Artikel

* [Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Integrierte Azure Active Directory-Rollen](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365-Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles)
