---
title: Kaufen von Apps von Drittanbietern für Teams
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
description: Erfahren Sie, wie Sie Apps von Drittanbietern für Teams im Microsoft Teams Admin Center kaufen.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3b90af2e0fecba2d6c421a5b26547e93b18df05d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196179"
---
<a name="purchase-third-party-apps-for-teams"></a>Kaufen von Apps von Drittanbietern für Teams
======================================================

> [!NOTE]
> Dieses Feature ist derzeit nur in den USA verfügbar.

Teams-Apps können kostenlos installiert werden, und einige erfordern möglicherweise den Kauf von Serviceabonnements, um den vollen Funktionsumfang und Umfang der App zu nutzen. Diese Dienstabonnements werden als Software as a Service (SaaS)-Angebote bezeichnet, die über [AppSource](https://appsource.microsoft.com/) und jetzt über das Microsoft Teams Admin Center erhältlich sind.

Auf [der Seite "Apps](manage-apps.md) verwalten" im Microsoft Teams Admin Center können Sie alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Sie können z. B. den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps in den App Store Ihrer Organisation hochladen, Apps auf Organisationsebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Hier können Sie auch Lizenzen für Dienste kaufen, die von Apps von Drittanbietern für Benutzer in Ihrer Organisation angeboten werden. Die **Spalte "Lizenzen"** in der Tabelle gibt an, ob eine App ein -Abonnement zum Kauf anbietet.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Screenshot mit Apps von Drittanbietern, die über Eins-/Abos verfügen":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Suchen nach und Erwerben von Diensten für eine Drittanbieter-App

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".** Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Suchen Sie nach der App, die Sie verwenden möchten. Um Apps zu identifizieren, die über ein kostenpflichtiges SaaS-Abonnement verfügen, suchen Sie in der Spalte **"Lizenzen".** Jede App hat einen der folgenden Werte:
    - **Jetzt kaufen:** Die App bietet ein SaaS-Abonnement und ist zum Kauf verfügbar.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **–**: Die App bietet kein SaaS-Abonnement an.
3. Wenn Sie die App finden, klicken  Sie auf **"Jetzt** kaufen", um auf der Seite mit den App-Details zur Registerkarte "Pläne und Preise" zu wechseln. Überprüfen Sie die Pläne und Preisinformationen für das Angebot von SaaS für die App. Wenn Sie weitere Informationen  benötigen, klicken Sie auf den Link "Weitere Informationen", um zur Seite der App in ["AppSource" zu wechseln.](https://appsource.microsoft.com/)  
4. Um einen Plan zu kaufen, klicken Sie **auf "Jetzt kaufen".** Sie werden zur Einkaufserfahrung für das Mit der App "Teams" verknüpfte Angebot weitergeleitet. Hier schließen Sie den Kauf des Diensts oder des SaaS-Angebots ab.
5. Wählen Sie den plan aus, den Sie wünschen. Wenn das Angebot von SaaS mehrere Pläne enthält, klicken Sie auf "Ändern", **um** die Liste der verfügbaren Pläne zu sehen.
6. Wählen Sie Ihre Abrechnungslaufzeit **(monatlich** oder **jährlich)** aus, und geben Sie dann die Anzahl der Benutzerlizenzen ein, die Sie kaufen möchten.
7. Geben Sie Ihre Zahlungsmethode ein.
8. Wenn Sie fertig sind, wählen Sie **"Bestellung bestellen" aus.**
9. Klicken Sie **auf "Jetzt konfigurieren",** um Ihr Abonnement auf der Website des Herausgebers zu aktivieren.

Nachdem Sie das mit der Teams-App verknüpfte SaaS-Angebot erworben  haben, können Sie die folgenden Kaufdetails auf der Registerkarte "Pläne und Preise" auf der Seite mit den App-Details anzeigen.

- **Aktivierungsdatum der Lizenz:** Datum, an dem Ihre Lizenz aktiviert wurde. Wenn Ihr Konto noch nicht eingerichtet ist, wird dies als Abonnementaktivierung angezeigt, **deren Aktivierung aussteht.**
- **Lizenzen:** Anzahl der erworbenen Lizenzen.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Screenshot der Registerkarte "Pläne und Preise" auf der Seite "App-Details"":::

Wählen **Sie "Lizenzen verwalten"** aus, um zum Microsoft 365 Admin Center zu wechseln, um die erworbenen Lizenzen anzeigen und verwalten zu können und um Lizenzzuweisungen für Benutzer zu verwalten.

Globale Administratoren können die Von jedem in der Organisation getätigten Einkäufe anzeigen, während Teams Serviceadministratoren nur die von sich selbst getätigten Einkäufe anzeigen können.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Haben Sie ein SaaS-Angebot für eine Teams-App, die Sie im Microsoft Teams Admin Center und in AppSource auflisten und verkaufen möchten?

Entwickler können mit ihren Team-Apps verknüpfte SaaS-Angebote erstellen. Diese Angebote werden über [Partner Center veröffentlicht](https://partner.microsoft.com) und stehen Organisationen zum Kauf über [AppSource und](https://appsource.microsoft.com/) das Microsoft Teams Admin Center zur Verfügung.
 
Entwickler von Drittanbieter-Apps können zu ["Erstellen eines SaaS-Angebots"](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) wechseln, um weitere Informationen zu erhalten.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Erstellen eines Angebots für SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
