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
description: Ihr Teams- oder IT-Administrator kann den externen Zugriff für andere Domänen (Verbund) so konfigurieren, dass Benutzer aus diesen Domänen in Teams teilnehmen können.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 2739f1b7f97e39617471ecf292ecf9424a7ac396
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726864"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Verwaltung des externen Zugriffs in Microsoft Teams

Externer Zugriff ist eine Möglichkeit für Teams-Benutzer aus einer ganzen externen Domäne Sie zu finden, anrufen, mit Ihnen zu chatten und Besprechungen mit Ihnen in Teams einzurichten. Über externen Zugriff können Sie auch mit Personen aus anderen Organisationen kommunizieren, die noch Skype for Business (online oder lokal) bzw. Skype (in der Vorschau) verwenden.

Wenn Sie externen Benutzern hingegen den Zugriff auf Teams und Kanäle gewähren möchten, ist der Gastzugriff möglicherweise besser geeignet. Weitere Informationen zu den Unterschieden zwischen externem Zugriff und Gastzugriff finden Sie unter [Vergleich von externem Zugriff und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Verwenden Sie den externen Zugriff in folgenden Situationen:
  
- Sie haben Benutzer in verschiedenen Domänen, die zusammenarbeiten müssen. Beispielsweise arbeiten Rob@contoso.com und Ann@northwindtraders.com zusammen mit einigen anderen Personen in den Domänen „contoso.com" und „northwindtraders.com" an einem Projekt.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Microsoft Teams zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Microsoft Teams-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. 

> [!IMPORTANT]
> Um den Teams-Client für die Kommunikation mit einem externen Benutzer zu verwenden (unabhängig davon, ob dieser Benutzer Teams oder Skype for Business verwendet), muss der Teams-Benutzer in Skype for Business Online verwaltet werden.

## <a name="plan-for-external-access"></a>Plan für externen Zugriff

Der externe Zugriff ist in Teams standardmäßig aktiviert. Das bedeutet, dass Ihre Organisation mit allen externen Domänen kommunizieren kann. Wenn Sie blockierte Domänen hinzufügen, sind alle anderen Domänen zulässig, und wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Die Ausnahme von dieser Regel ist, wenn anonyme Teilnehmer in Besprechungen zugelassen werden. Es gibt drei Szenarien für das Einrichten des externen Zugriffs im Microsoft Teams Admin Center (**Organisationsweite Einstellungen** > **Externer Zugriff**):

> [!NOTE]
> Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

> [!NOTE]
> Wenn Sie den externen Zugriff in Ihrer Organisation deaktivieren, können externe Benutzer an Besprechungen dennoch über die anonyme Teilnahme teilnehmen. Weitere Informationen finden Sie unter [Verwalten von Besprechungseinstellungen in Teams](./meeting-settings-in-teams.md).

- **Offener Verbund**: Dies ist die Standardeinstellung in Teams, mit der Personen in Ihrer Organisation Sie finden, anrufen, mit Ihnen chatten und Besprechungen mit Personen in einer beliebigen Domäne außerhalb Ihrer Organisation einrichten können.

    In diesem Szenario können Ihre Benutzer mit allen externen Domänen kommunizieren, die Microsoft Teams oder Skype for Business ausführen UND den öffentlichen Verbund verwenden ODER Ihre Domäne zur Zulassungsliste hinzugefügt haben.

- **Bestimmte Domänen zulassen**: Indem Sie Domänen zu einer **Zulassungsliste** hinzufügen, beschränken Sie den externen Zugriff auf die erlaubten Domänen. Sobald Sie eine Liste der erlaubten Domänen eingerichtet haben, werden alle anderen Domänen gesperrt. Um bestimmte Domänen zuzulassen, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Zulässig** aus.

- **Bestimmte Domänen blockieren**: Indem Sie Domänen zu einer **Sperrliste** hinzufügen, können Sie mit allen externen Domänen *außer* den blockierten Domänen kommunizieren. Um bestimmte Domänen zu blockieren, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Blockiert** aus. Sobald Sie eine Liste blockierter Domänen erstellt haben, werden alle anderen Domänen zugelassen.

> [!NOTE]
> Die zugelassenen oder blockierten Domänen werden auf Besprechungen nur dann angewendet, wenn der anonyme Zugriff auf Besprechungen deaktiviert ist.

## <a name="allow-or-block-domains"></a>Zulassen oder Blockieren von Domänen

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Schritt 1: Aktivieren Ihrer Organisation für die Kommunikation mit einer anderen Microsoft Teams- oder Skype for Business-Organisation

![Ein Symbol mit dem Microsoft Teams-Logo.](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Organisationsweite Einstellungen** > **Externer Zugriff**.

2. Aktivieren Sie die Option **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren**.

     ![Screenshot der aktivierten Einstellung "Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren".](media/manage-external-access-2.png).

3. Wenn Sie allen Microsoft Teams-Organisationen die Kommunikation mit den Benutzern in Ihrer Organisation erlauben möchten, fahren Sie mit Schritt 5 fort.

4. Wenn Sie die Organisationen, die mit Benutzern in Ihrer Organisation kommunizieren können, einschränken möchten, können Sie entweder alle außer einigen bestimmten Domänen oder nur bestimmte Domänen zulassen. 

    - Wenn Sie alle außer einigen Domänen zulassen möchten, wählen Sie die zu blockierenden Domänen aus, indem Sie auf **Domäne hinzufügen** klicken. Geben Sie im Bereich **Domäne hinzufügen** den Domänennamen ein, klicken Sie auf **Blockiert** und dann auf **Fertig**. 
    - Wenn Sie die Kommunikation auf bestimmte Organisationen einschränken möchten, fügen Sie diese Domänen zur Liste mit dem Status **Zulässig** hinzu. Sobald Sie eine Domäne zur der Zulassungsliste hinzugefügt haben, wird die Kommunikationen mit anderen Organisationen auf die Organisationen beschränkt, die sich in der Zulassungsliste befinden. 

5. Klicken Sie auf **Speichern**.

6. Stellen Sie sicher, dass der Administrator in der andere Microsoft Teams-Organisation die gleichen Schritte ausführt. Ist in der anderen Organisation beispielsweise die Kommunikation mit Benutzern anderer Organisationen eingeschränkt, muss der Administrator der anderen Organisation die Domäne Ihres Unternehmens zur Liste der **zulässigen Domänen** hinzufügen.

### <a name="step-2---test-it"></a>Schritt 2: Testen

Um Ihr Setup zu testen, benötigen Sie einen Microsoft Teams-Benutzer, der sich nicht hinter der Firewall befindet.
  
1. Nachdem Sie und der Administrator der Organisation die Einstellungen für den **externen Zugriff** geändert haben, sollte es funktionieren.

2. Suchen Sie in der Teams-App anhand der E-Mail-Adresse nach der Person, und senden Sie eine Chatanfrage.

3. Bitten Sie Ihren Microsoft Teams-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, liegt das Problem bei den Firewalleinstellungen (vorausgesetzt, Ihr Kontakt hat die eigenen Firewalleinstellungen bereits überprüft).

4. Eine weitere Möglichkeit zu testen, ob das Problem bei der Firewall liegt, besteht darin, an einen WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel ein Café). Senden Sie von dort mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht zugestellt werden kann, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

> [!NOTE]
> Wenn Sie und ein anderer Benutzer sowohl den externen Zugriff aktivieren als auch die Domänen des anderen zulassen, funktioniert das. Wenn es nicht funktioniert, sollte der andere Benutzer sich vergewissern, dass seine Konfiguration Ihre Domäne nicht blockiert.


## <a name="communicate-with-skype-users-in-preview"></a>Kommunizieren mit Skype-Benutzern (in der Vorschau)

Führen Sie die folgenden Schritte aus, damit Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern chatten und diese anrufen können. Teams-Benutzer können dann nach schriftlichen Einzelunterhaltungen oder Audio/Video-Anrufen mit Skype-Benutzern suchen und diese starten.

![Ein Symbol mit dem Microsoft Teams-Logo.](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Organisationsweite Einstellungen** > **Externer Zugriff**.

2. Aktivieren Sie die Einstellung **Benutzer können mit Skype-Benutzern kommunizieren**.

    ![Screenshot der aktivierten Einstellung "Benutzer können mit Skype-Benutzern kommunizieren".](media/manage-external-access-5.png).

Weitere Informationen über die Möglichkeiten der Kommunikation zwischen Teams- und Skype-Benutzern, einschließlich der Einschränkungen, finden Sie unter [Interoperabilität von Teams und Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Häufige Szenarien für den externen Zugriff

In den folgenden Abschnitten wird beschrieben, wie Sie den Partnerverbund für gängige externe Zugriffsszenarien aktivieren und wie die TeamsUpgradePolicy die Zustellung eingehender Chats und Anrufe bestimmt.

### <a name="enable-federation"></a>Aktivieren des Partnerverbunds

Damit Benutzer in Ihrer Organisation mit Benutzern in einer anderen Organisation kommunizieren können, müssen beide Organisationen den Partnerverbund aktivieren. Die Schritte zur Aktivierung des Partnerverbunds für eine bestimmte Organisation hängen davon ab, ob es sich um eine reine Online-, eine Hybrid- oder eine reine lokale Organisation handelt.

| Wenn Ihre Organisation | Aktivieren Sie den Partnerverbund wie folgt |
|:---------|:-----------------------|
|Online ohne lokales Skype for Business. Dazu gehören Organisationen mit TeamsOnly-Benutzern und/oder Skype for Business Online-Benutzern.| Wird Teams Admin Center verwendet: <br>– Stellen Sie sicher, dass die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter „Externer Zugriff“ aktiviert ist.<br>– Wenn Sie keinen offenen Partnerverbund verwenden (der den Verbund mit einer beliebigen anderen Domäne zulässt), dann fügen Sie die externe Domäne zur Liste „Zulässig“ hinzu.<br><br>Wird PowerShell verwendet:<br>– Stellen Sie sicher, dass der Mandant für den Verbund aktiviert ist: `Get-CsTenantFederationConfiguration` muss `AllowFederatedUsers=true` anzeigen. <br>– Stellen Sie sicher, dass der effektive Wert `CsExternalAccessPolicy` des Benutzers `EnableFederationAccess=true` aufweist.<br>– Wenn Sie keinen offenen Verbund verwenden, stellen Sie sicher, dass die Zieldomäne in `AllowedDomains` von `CsTenantFederationConfiguration` enthalten ist. |
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
| Nur online ohne lokales Skype for Business.  Dazu gehören Organisationen mit TeamsOnly-Benutzern und/oder Skype for Business Online-Benutzern. | Wird Teams Admin Center verwendet: <br>– Stellen Sie sicher, dass die Einstellung **Benutzer können mit Skype-Benutzern kommunizieren** unter „Externer Zugriff“ aktiviert ist.<br><br>Wird PowerShell verwendet: <br>– Stellen Sie sicher, dass der Mandant für den Verbund aktiviert ist: `Get-CsTenantFederationConfiguration` muss `AllowPublicUsers=true` anzeigen. <br> – Stellen Sie sicher, dass der effektive Wert `CsExternalAccessPolicy` des Benutzers `EnablePublicCloudAccess=true` aufweist. |
| Reine lokale Organisation | In lokalen Tools: <br> – Stellen Sie sicher, dass Skype als Verbundpartner aktiviert ist. <br> – Stellen Sie sicher, dass der `EnablePublicCloudAccess=true` für den Benutzer über `ExternalAccessPolicy` aktiviert ist (entweder über die globale Richtlinie, die Standortrichtlinie oder die dem Benutzer zugewiesene Richtlinie).|
| Hybridorganisation mit einigen Onlinebenutzern (entweder in Skype for Business oder Teams) und einigen lokalen Benutzern.| Führen Sie die oben stehenden Schritte sowohl für die Online- als auch die lokale Organisation aus.


> [!IMPORTANT]
> Sie müssen keine **Skype-Domänen** als zulässige Domänen hinzufügen, um es Microsoft Teams- oder Skype for Business Online-Benutzern zu ermöglichen, mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation zu kommunizieren. Alle **Skype-Domänen** sind erlaubt.

## <a name="how-does-external-access-compare-with-guest-access"></a>Inwiefern unterscheidet sich der externe Zugriff vom Gastzugriff?

Wenn Sie mehr über den Unterschied zwischen externem Zugriff und Gastzugriff wissen möchten, lesen Sie [Kommunikation mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Verwandte Themen

- [Native Chaterfahrung für externe Benutzer (im Verbund)](native-chat-for-external-users.md)
