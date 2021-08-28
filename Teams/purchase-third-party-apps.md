---
title: Erwerben sie Apps von Drittanbietern für Teams
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
description: Informationen zum Erwerben von Drittanbieter-Apps für Teams Sie im Microsoft Teams Admin Center.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: da917d2c58282554e3e2a68464cea1f2249bd324
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616181"
---
# <a name="purchase-third-party-apps-for-teams"></a>Erwerben sie Apps von Drittanbietern für Teams

> [!NOTE]
> Dieses Feature ist derzeit nur in den USA verfügbar.

Teams-Apps können kostenlos installiert werden, und für einige ist möglicherweise der Kauf von Serviceabonnements erforderlich, um den vollen Funktionsumfang und Umfang der App zu nutzen. Diese Dienstabonnements werden als SaaS-Angebote (Software as a Service) bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das Microsoft Teams Admin Center erhältlich sind.

Auf [der Seite Apps](manage-apps.md) verwalten im Microsoft Teams Admin Center können Sie alle Ihre Teams für Ihre Organisation anzeigen und verwalten. So können Sie beispielsweise den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste kaufen, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die **Spalte Lizenzen** in der Tabelle gibt an, ob eine App ein SaaS-Abonnement zum Kauf anbietet.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot mit Apps von Drittanbietern, die SaaS-Abonnements haben":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Suchen nach und Kaufen von Diensten für eine Drittanbieter-App

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder ein Teams sein, um auf die Seite zugreifen zu können.
2. Suchen Sie nach der App, die Sie verwenden möchten. Um Apps mit einem kostenpflichtigen SaaS-Abonnement zu identifizieren, sehen Sie in der Spalte **Lizenzen** nach. Jede App hat einen der folgenden Werte:
    - **Jetzt kaufen:** Die App bietet ein SaaS-Abonnement und kann jetzt kaufen werden.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **- –**: Die App bietet kein SaaS-Abonnement an.
3. Wenn Sie die App finden, klicken  Sie auf **Jetzt** kaufen, um auf der Seite mit den App-Details zur Registerkarte Pläne und Preise zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das SaaS-Angebot für die App. Wenn Sie weitere Informationen  benötigen, klicken Sie auf den Link Weitere Informationen, um zur App-Seite in [AppSource zu wechseln.](https://appsource.microsoft.com/)  
4. Um einen Plan zu kaufen, klicken Sie **auf Jetzt kaufen**. Sie werden zur Einkaufserfahrung für das Angebot weitergeleitet, das mit der App Teams ist. Hier schließen Sie den Kauf des Diensts oder SaaS-Angebots ab.
5. Wählen Sie den plan aus. Wenn das SaaS-Angebot mehrere Pläne umfasst, klicken Sie **auf Ändern,** um die Liste der verfügbaren Pläne zu sehen.
6. Wählen Sie Ihre Abrechnungslaufzeit **(monatlich** oder **jährlich)** aus, und geben Sie dann die Anzahl der Benutzerlizenzen ein, die Sie kaufen möchten.
7. Geben Sie Ihre Zahlungsmethode ein.
8. Wenn Sie fertig sind, wählen Sie **Bestellung bestellen aus.**
9. Klicken **Sie auf Jetzt** konfigurieren, um Ihr Abonnement auf der Website des Herausgebers zu aktivieren.

Nachdem Sie das SaaS-Angebot erworben haben, das der Teams-App zugeordnet ist, können Sie auf der Seite mit den App-Details auf der Registerkarte Pläne und Preise die folgenden Kaufdetails anzeigen. 

- **Datum der Lizenzaktivierung:** Das Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird dies als **Abonnement aktivierung ausstehend angezeigt.**
- **Lizenzen:** Anzahl der erworbenen Lizenzen.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte "Pläne und Preise" auf der Seite "App-Details"":::

Wählen **Sie Lizenzen verwalten** aus, um zum Microsoft 365 Admin Center zu wechseln, um die erworbenen Lizenzen anzeigen und zu verwalten und um Lizenzzuweisungen für Benutzer zu verwalten.

Globale Administratoren können die Von jedem in der Organisation getätigten Einkäufe anzeigen, während Teams Dienstadministratoren nur die von sich selbst getätigten Einkäufe anzeigen können.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Haben Sie ein SaaS-Angebot für Teams-App, die Sie im Admin Center Microsoft Teams AppSource auflisten und verkaufen möchten?

Entwickler können SaaS-Angebote erstellen, die ihren Apps Teams sind. Diese Angebote werden über [Partner Center veröffentlicht](https://partner.microsoft.com) und stehen Organisationen zum Kauf über [AppSource](https://appsource.microsoft.com/) und Microsoft Teams Admin Center zur Verfügung.
 
App-Entwickler von Drittanbietern finden weitere Informationen unter Erstellen [eines SaaS-Angebots.](/azure/marketplace/partner-center-portal/create-new-saas-offer)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Erstellen eines SaaS-Angebots](/azure/marketplace/partner-center-portal/create-new-saas-offer)