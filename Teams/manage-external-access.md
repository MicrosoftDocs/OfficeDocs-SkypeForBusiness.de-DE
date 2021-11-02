---
title: Verwaltung des externen Zugriffs (Partnerverbund)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Ihr Microsoft Teams- oder IT-Administrator kann den externen Zugriff für andere Domänen (Verbund) so konfigurieren, dass Benutzer aus diesen Domänen nach Ihren Benutzern suchen, mit ihnen telefonieren und chatten sowie Besprechungen einrichten können.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ee2492038ac05f54d1846703851846bef95893eb
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634924"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Verwaltung des externen Zugriffs in Microsoft Teams

Der externe Zugriff ermöglicht es Microsoft Teams-Benutzern von außerhalb Ihrer Organisation, in Microsoft Teams nach Ihnen zu suchen, mit Ihnen zu telefonieren und zu chatten sowie Besprechungen einzurichten. Über externen Zugriff können Sie auch mit Personen aus anderen Organisationen kommunizieren, die noch Skype for Business (online oder lokal) bzw. Skype (in der Vorschau) verwenden.

Wenn Sie externen Benutzern hingegen den Zugriff auf Ihre Teams und Kanäle gewähren möchten, verwenden Sie stattdessen den Gastzugriff. Weitere Informationen zu den Unterschieden zwischen externem Zugriff und Gastzugriff finden Sie unter [Vergleich von externem Zugriff und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Verwenden Sie den externen Zugriff in folgenden Situationen:
  
- Verschiedene Benutzer in externen Domänen müssen zusammenarbeiten können. Beispiel: Rob@contoso.com und Ann@northwindtraders.com arbeiten mit einigen anderen Personen in den Domänen „contoso.com" und „northwindtraders.com" an einem Projekt zusammen.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Microsoft Teams zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Microsoft Teams-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. 

## <a name="plan-for-external-access"></a>Plan für externen Zugriff

Der externe Zugriff ist in Teams standardmäßig aktiviert. Das bedeutet, dass Ihre Organisation mit allen externen Domänen kommunizieren kann. Wenn Sie blockierte Domänen hinzufügen, sind alle anderen Domänen zulässig, und wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Die Ausnahme von dieser Regel ist, wenn anonyme Teilnehmer in Besprechungen zugelassen werden. Es gibt drei Szenarien für das Einrichten des externen Zugriffs im Microsoft Teams Admin Center (**Benutzer** > **Externer Zugriff**):

> [!NOTE]
> Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

> [!NOTE]
> Wenn Sie den externen Zugriff in Ihrer Organisation deaktivieren, können externe Benutzer an Besprechungen dennoch über die anonyme Teilnahme teilnehmen. Weitere Informationen finden Sie unter [Verwalten von Besprechungseinstellungen in Teams](meeting-settings-in-teams.md).

- **Alle externen Domänen zulassen**: Dies ist die Standardeinstellung in Microsoft Teams, die es Personen in Ihrer Organisation erlaubt, nach Personen in einer beliebigen Domäne außerhalb Ihrer Organisation zu suchen, mit ihnen zu telefonieren oder zu chatten und Besprechungen einzurichten.

    In diesem Szenario können Ihre Benutzer mit allen externen Domänen kommunizieren, die Microsoft Teams oder Skype for Business ausführen bzw. externe Domänen zulassen oder Ihre Domäne zu ihrer Zulassungsliste hinzugefügt haben.

- **Nur bestimmte externe Domänen zulassen**: Durch das Hinzufügen von Domänen zu einer **Zulassungsliste** beschränken Sie den externen Zugriff auf diese erlaubten Domänen. Sobald Sie eine Liste der erlaubten Domänen eingerichtet haben, werden alle anderen Domänen gesperrt. Um bestimmte Domänen zuzulassen, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Zulässig** aus.

- **Bestimmte Domänen blockieren**: Indem Sie Domänen zu einer **Sperrliste** hinzufügen, können Sie mit allen externen Domänen *außer* den blockierten Domänen kommunizieren. Um bestimmte Domänen zu blockieren, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Blockiert** aus. Sobald Sie eine Liste blockierter Domänen erstellt haben, werden alle anderen Domänen zugelassen.

- **Alle externen Domänen blockieren**: Verhindert, dass Personen in Ihrer Organisation nach Personen in einer Domäne außerhalb Ihrer Organisation suchen, mit ihnen telefonieren, chatten und Besprechungen einrichten.

> [!NOTE]
> Die zugelassenen oder blockierten Domänen werden auf Besprechungen nur dann angewendet, wenn der anonyme Zugriff auf Besprechungen deaktiviert ist.

## <a name="allow-or-block-domains"></a>Zulassen oder Blockieren von Domänen

  **Verwenden des Microsoft Teams Admin Centers**

Vorgehensweise, um bestimmte Domänen zuzulassen

1. Wechseln Sie im Microsoft Teams Admin Center zu **Benutzer** > **Externer Zugriff**.

2. Wählen Sie unter **Wählen Sie aus, auf welche Domänen Ihre Benutzer Zugriff haben** die Option **Nur bestimmte externe Domänen zulassen** aus.

3. Wählen Sie **Domänen zulassen** aus.

4. Geben Sie im Feld **Domäne** die Domäne ein, die Sie zulassen möchten, und klicken Sie dann auf **Fertig**.

5. Wenn Sie eine weitere Domäne zulassen möchten, klicken Sie auf **Domäne hinzufügen**.

6. Klicken Sie auf **Speichern**.

Vorgehensweise, um bestimmte Domänen zu blockieren

1. Wechseln Sie im Microsoft Teams Admin Center zu **Benutzer** > **Externer Zugriff**.

2. Wählen Sie unter **Wählen Sie aus, auf welche Domänen Ihre Benutzer Zugriff haben** die Option **Nur bestimmte externe Domänen blockieren** aus.

3. Wählen Sie **Domänen blockieren** aus.

4. Geben Sie im Feld **Domäne** die Domäne ein, die Sie zulassen möchten, und klicken Sie dann auf **Fertig**.

5. Wenn Sie eine weitere Domäne blockieren möchten, klicken Sie auf **Domäne hinzufügen**.

6. Klicken Sie auf **Speichern**.

Stellen Sie sicher, dass der Administrator in der anderen Microsoft Teams-Organisation die gleichen Schritte ausführt. Ist in der anderen Organisation beispielsweise die Kommunikation mit Benutzern anderer Organisationen eingeschränkt, muss der Administrator der anderen Organisation die Domäne Ihres Unternehmens zur Liste der **zulässigen Domänen** hinzufügen.

## <a name="communicate-with-skype-users-preview"></a>Kommunizieren mit Skype-Benutzern (Vorschau)

Führen Sie die folgenden Schritte aus, damit Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern chatten und diese anrufen können. Teams-Benutzer können dann nach schriftlichen Einzelunterhaltungen oder Audio/Video-Anrufen mit Skype-Benutzern suchen und diese starten.

  **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie im linken Navigationsbereich zu **Benutzer** > **Externer Zugriff**.

2. Aktivieren Sie die Einstellung **Benutzern in meiner Organisation erlauben, mit Skype-Benutzern zu kommunizieren**.

Weitere Informationen über die Möglichkeiten der Kommunikation zwischen Teams- und Skype-Benutzern, einschließlich der Einschränkungen, finden Sie unter [Interoperabilität von Teams und Skype](teams-skype-interop.md).

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>Unerwünschte Kontakt mit externen, nicht verwalteten Teams-Benutzern blockieren

Führen Sie diese Schritte aus, um Teams-Benutzer in Ihrer Organisation vor unerwünschten Kontakten mit externen Teams-Benutzern zu schützen, deren Konten nicht von einer Organisation verwaltet werden.

  **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie im linken Navigationsbereich zu **Benutzer** > **Externer Zugriff**.

2. Führen Sie einen der folgenden Schritte durch:

    - Um zu verhindern, dass Teams-Benutzer in Ihrer Organisation mit externen Teams-Benutzern kommunizieren, deren Konten nicht von einer Organisation verwaltet werden, deaktivieren Sie die Einstellung **Benutzer in meiner Organisation können mit Teams-Benutzern kommunizieren, deren Konten nicht von einer Organisation verwaltet werden** und löschen Sie das Kontrollkästchen **Externe Benutzer mit Teams-Konten, die nicht von einer Organisation verwaltet werden, können Benutzer in meiner Organisation kontaktieren**.

    - Damit Teams-Benutzer in Ihrer Organisation mit externen Teams-Benutzern kommunizieren können, deren Konten nicht von einer Organisation verwaltet werden, wenn Ihre Teams-Benutzer den Kontakt initiiert haben, aktivieren Sie die Einstellung **Benutzer in meiner Organisation können mit Teams-Benutzern kommunizieren, deren Konten nicht von einer Organisation verwaltet werden** und löschen Sie das Kontrollkästchen **Externe Benutzer mit Teams-Konten, die nicht von einer Organisation verwaltet werden, können Benutzer in meiner Organisation kontaktieren**.

    - Damit Teams-Benutzer in Ihrer Organisation mit externen Teams-Benutzern kommunizieren können, deren Konten nicht von einer Organisation verwaltet werden, und Anforderungen zur Kommunikation mit diesen externen Teams-Benutzern erhalten, aktivieren Sie die Einstellung **Benutzer in meiner Organisation können mit Teams-Benutzern kommunizieren, deren Konten nicht von einer Organisation verwaltet werden** und markieren Sie das Kontrollkästchen **Externe Benutzer mit Teams-Konten, die nicht von einer Organisation verwaltet werden, können Benutzer in meiner Organisation kontaktieren**.

## <a name="test-access"></a>Zugriff testen

Um Ihr Setup zu testen, benötigen Sie einen Microsoft Teams-Benutzer, der sich nicht hinter der Firewall befindet.
  
1. Nachdem Sie und der Administrator der Organisation die Einstellungen für den **externen Zugriff** geändert haben, sollte es funktionieren.

2. Suchen Sie in der Teams-App anhand der E-Mail-Adresse nach der Person, und senden Sie eine Chatanfrage.

3. Bitten Sie Ihren Microsoft Teams-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, liegt das Problem bei den Firewalleinstellungen (vorausgesetzt, Ihr Kontakt hat die eigenen Firewalleinstellungen bereits überprüft).

4. Eine weitere Möglichkeit zu testen, ob das Problem bei der Firewall liegt, besteht darin, an einen WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel ein Café). Senden Sie von dort mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht zugestellt werden kann, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

> [!NOTE]
> Wenn Sie und ein anderer Benutzer sowohl den externen Zugriff aktivieren als auch die Domänen des anderen zulassen, funktioniert das. Wenn es nicht funktioniert, sollte der andere Benutzer sich vergewissern, dass seine Konfiguration Ihre Domäne nicht blockiert.

## <a name="common-external-access-scenarios"></a>Häufige Szenarien für den externen Zugriff

In den folgenden Abschnitten wird beschrieben, wie Sie den Partnerverbund für gängige externe Zugriffsszenarien aktivieren und wie die TeamsUpgradePolicy die Zustellung eingehender Chats und Anrufe bestimmt.

### <a name="enable-federation"></a>Aktivieren des Partnerverbunds

Damit Benutzer in Ihrer Organisation mit Benutzern in einer anderen Organisation kommunizieren können, müssen beide Organisationen den Partnerverbund aktivieren. Die Schritte zur Aktivierung des Partnerverbunds für eine bestimmte Organisation hängen davon ab, ob es sich um eine reine Online-, eine Hybrid- oder eine reine lokale Organisation handelt.

| Wenn Ihre Organisation | Aktivieren Sie den Partnerverbund wie folgt |
|:---------|:-----------------------|
|Online ohne lokales Skype for Business. Dazu gehören Organisationen mit TeamsOnly-Benutzern und/oder Skype for Business Online-Benutzern.| Wird Teams Admin Center verwendet: <br>– Stellen Sie sicher, dass die Domänen, mit denen Sie kommunizieren möchten, in "Externer Zugriff" zulässig sind.<br><br>Wird PowerShell verwendet:<br>– Stellen Sie sicher, dass der Mandant für den Verbund aktiviert ist: `Get-CsTenantFederationConfiguration` muss `AllowFederatedUsers=true` anzeigen. <br>– Stellen Sie sicher, dass der effektive Wert `CsExternalAccessPolicy` des Benutzers `EnableFederationAccess=true` aufweist.<br>– Wenn Sie keinen offenen Verbund verwenden, stellen Sie sicher, dass die Zieldomäne in `AllowedDomains` von `CsTenantFederationConfiguration` enthalten ist. |
|Reine lokale Organisation | In lokalen Tools: <br>– Stellen Sie sicher, dass der Partnerverbund in `CsAccessEdgeConfiguration` aktiviert ist.<br>– Stellen Sie sicher, dass der Partnerverbund für den Benutzer über `ExternalAccessPolicy` aktiviert ist (entweder über die globale Richtlinie, die Standortrichtlinie oder die dem Benutzer zugewiesene Richtlinie). <br> – Wenn Sie keinen offenen Verbund verwenden, stellen Sie sicher, dass die Zieldomäne in `AllowedDomains` enthalten ist. |
|Hybridorganisation mit einigen Onlinebenutzern (entweder in Skype for Business oder Teams) und einigen lokalen Benutzern. | Führen Sie die oben stehenden Schritte sowohl für die Online- als auch die lokale Organisation aus. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Zustellung von eingehenden Chats und Anrufen 

Eingehende Chats und Anrufe von einer Verbundorganisation landen im Teams- oder Skype for Business-Client des Benutzers, je nach dem Modus des empfangenden Benutzers in TeamsUpgradePolicy.

| Sie möchten | Gehen Sie so vor: |
|:---------|:-----------------------|
| Sicherstellen, dass eingehende Verbundchats und -anrufe im Teams-Client des Benutzers ankommen: | Konfigurieren Sie für Ihre Benutzer den „TeamsOnly“-Modus.
| Sicherstellen, dass eingehende Verbundchats und -anrufe im Skype for Business-Client des Benutzers ankommen: | Konfigurieren Sie für Ihre Benutzer einen beliebigen Modus außer „TeamsOnly“. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Aktivieren des Partnerverbunds zwischen Benutzern in Ihrer Organisation und Endbenutzern von Skype

So aktivieren Sie den Partnerverbund zwischen Benutzern in Ihrer Organisation und Verbrauchern mit Skype:

| Wenn Ihre Organisation | Aktivieren Sie den Verbraucherverbund wie folgt |
|:---------|:-----------------------|
| Nur online ohne lokales Skype for Business.  Dazu gehören Organisationen mit TeamsOnly-Benutzern und/oder Skype for Business Online-Benutzern. | Wird Teams Admin Center verwendet: <br>– Stellen Sie sicher, dass **Benutzern in meiner Organisation erlauben, mit Skype-Benutzern zu kommunizieren** in "Externer Zugriff" aktiviert ist.<br><br>Wird PowerShell verwendet: <br>– Stellen Sie sicher, dass der Mandant für den Verbund aktiviert ist: `Get-CsTenantFederationConfiguration` muss `AllowPublicUsers=true` anzeigen. <br> – Stellen Sie sicher, dass der effektive Wert `CsExternalAccessPolicy` des Benutzers `EnablePublicCloudAccess=true` aufweist. |
| Reine lokale Organisation | In lokalen Tools: <br> – Stellen Sie sicher, dass Skype als Verbundpartner aktiviert ist. <br> – Stellen Sie sicher, dass der `EnablePublicCloudAccess=true` für den Benutzer über `ExternalAccessPolicy` aktiviert ist (entweder über die globale Richtlinie, die Standortrichtlinie oder die dem Benutzer zugewiesene Richtlinie).|
| Hybridorganisation mit einigen Onlinebenutzern (entweder in Skype for Business oder Teams) und einigen lokalen Benutzern.| Führen Sie die oben stehenden Schritte sowohl für die Online- als auch die lokale Organisation aus.


> [!IMPORTANT]
> Sie müssen keine **Skype-Domänen** als zulässige Domänen hinzufügen, um es Microsoft Teams- oder Skype for Business Online-Benutzern zu ermöglichen, mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation zu kommunizieren. Es sind alle **Skype-Domänen** zulässig.

## <a name="federation-diagnostic-tool"></a>Partnerverbund-Diagnosetool

Wenn Sie ein Administrator sind, können Sie mit dem folgenden Diagnosetool überprüfen, ob ein Teams mit einem verbundenen Benutzer Teams kommunizieren kann:

1. Wählen Sie unten **Tests ausführen** aus, um das Diagnosetool im Microsoft 365 Admin füllen. 

   > [!div class="nextstepaction"]
   > [Ausführen von Tests: Teams Partnerverbund](https://aka.ms/TeamsFederationDiag)

2. Geben Sie im Bereich „Diagnose ausführen“ die **SIP-Adresse (Session Initiation Protocol)** und den **Domänennamen des Partnermandanten** ein, und wählen Sie dann **Tests ausführen** aus.

3. Die Tests geben die besten nächsten Schritte zurück, um alle Mandanten- oder Richtlinienkonfigurationen zu adressieren, die die Kommunikation mit dem Partnerbenutzer verhindern.


## <a name="related-topics"></a>Verwandte Themen

- [Native Chaterfahrung für externe Benutzer (im Verbund)](native-chat-for-external-users.md)
