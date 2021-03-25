---
title: Kaufen von Drittanbieter-Apps für Teams
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie Apps von Drittanbietern für Teams im Microsoft Teams Admin Center erwerben.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 57530ec952b6bbe806e685d0980fcee3a21d1887
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117683"
---
<a name="purchase-third-party-apps-for-teams"></a>Kaufen von Drittanbieter-Apps für Teams
======================================================

> [!NOTE]
> Dieses Feature ist derzeit nur in den USA verfügbar.

Teams-Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Dienstabonnements, um die volle Funktionalität und den Umfang der App zu nutzen. Diese Dienstabonnements werden als Software as a Service (SaaS)-Angebote bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das Microsoft Teams Admin Center zum Kauf verfügbar sind.

Auf [der Seite](manage-apps.md) "Apps verwalten" im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste erwerben, die von Apps von Drittanbietern für Benutzer in Ihrer Organisation angeboten werden. Die **Spalte Lizenzen** in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot mit Apps von Drittanbietern mit SaaS-Abonnements":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Suchen und Erwerben von Diensten für eine Drittanbieter-App

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Suchen Sie nach der app, die Sie wünschen. Wenn Sie Apps mit einem kostenpflichtigen SaaS-Abonnement identifizieren möchten, suchen Sie in der Spalte **Lizenzen** nach. Jede App hat einen der folgenden Werte:
    - **Jetzt kaufen:** Die App bietet ein SaaS-Abonnement und steht zum Kauf zur Verfügung.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **- -**: Die App bietet kein SaaS-Abonnement an.
3. Wenn Sie die App finden, klicken  Sie auf Jetzt **kaufen,** um zur Registerkarte Pläne und Preise auf der Seite mit den App-Details zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen benötigen, klicken Sie auf **den** Link Weitere Informationen, um zur Seite der App auf [AppSource zu wechseln.](https://appsource.microsoft.com/)  
4. Wenn Sie einen Plan kaufen möchten, klicken Sie **auf Jetzt kaufen.** Sie werden zur Einkaufserfahrung für das Angebot weitergeleitet, das der Teams-App zugeordnet ist. Hier schließen Sie Den Kauf des Diensts oder des SaaS-Angebots ab.
5. Wählen Sie den plan aus, den Sie wünschen. Wenn das SaaS-Angebot mehrere Pläne enthält, klicken Sie auf Ändern, **um** die Liste der verfügbaren Pläne zu sehen.
6. Wählen Sie Ihren Abrechnungszeitraum **(monatlich** oder **jährlich)** aus, und geben Sie dann die Anzahl der Benutzerlizenzen ein, die Sie kaufen möchten.
7. Geben Sie Ihre Zahlungsmethode ein.
8. Wenn Sie fertig sind, wählen Sie **Bestellung platzieren aus.**
9. Klicken **Sie auf Jetzt konfigurieren,** um Ihr Abonnement auf der Website des Herausgebers zu aktivieren.

Nachdem Sie das mit der Teams-App verknüpfte SaaS-Angebot erworben  haben, können Sie die folgenden Kaufdetails auf der Registerkarte Pläne und Preise auf der Seite mit den App-Details anzeigen.

- **Datum der Lizenzaktivierung:** Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird dies als **Aktivierung ausstehender Abonnements angezeigt.**
- **Lizenzen:** Anzahl der lizenzen, die Sie erworben haben.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte "Pläne und Preise" auf der Seite "App-Details"":::

Wählen **Sie Lizenzen verwalten** aus, um zum Microsoft 365 Admin Center zu wechseln, um die erworbenen Lizenzen ein- und zu verwalten sowie Lizenzzuweisungen für Benutzer zu verwalten.

Globale Administratoren können die einkäufe anzeigen, die von jedem in der Organisation getätigt wurden, während Teams-Dienstadministratoren nur die selbst getätigten Einkäufe anzeigen können.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Haben Sie ein SaaS-Angebot für eine Teams-App, die Sie im Microsoft Teams Admin Center und appSource auflisten und verkaufen möchten?

Entwickler können SaaS-Angebote erstellen, die ihren Teams-Apps zugeordnet sind. Diese Angebote werden im [Partner Center veröffentlicht](https://partner.microsoft.com) und stehen Organisationen über [AppSource](https://appsource.microsoft.com/) und das Microsoft Teams Admin Center zur Verfügung.
 
Entwickler von Drittanbieter-Apps finden weitere Informationen unter Erstellen eines [SaaS-Angebots.](/azure/marketplace/partner-center-portal/create-new-saas-offer)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)