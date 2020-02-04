---
title: Einrichten von Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: 'Erfahren Sie, wie Sie Ihre Domäne, Benutzer, Chat-Nachrichten und Anwesenheitsinformationen für Ihr Unternehmen einrichten müssen, um Skype for Business zu installieren. Erfahren Sie außerdem, wie Sie Audio-Konferenzen, das Telefonsystem und Anrufpläne sowie Skype-Livekonferenzen einrichten können. '
ms.openlocfilehash: d30a141b80ade00ef03bafdfab388df56e4b1b7d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692870"
---
# <a name="set-up-skype-for-business-online"></a>Einrichten von Skype for Business Online.

Sie müssen über die Berechtigungen eines globalen Administrators für Office 365 verfügen, um Skype for Business einzurichten. Wenn der Zugriff auf das Internet jedoch durch eine Firewall oder einen Proxyserver eingeschränkt wird, können Sie einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) zur Einrichtung von Skype for Business heranziehen.

## <a name="setting-up-skype"></a>Einrichten von Skype

Es sieht so aus, als würden Sie Hilfe beim Einrichten von Skype mit Ihrem Office 365-Abonnement benötigen. Indem Sie die in diesem Artikel angeführten Schritte ausführen, können Sie das Einrichten abschließen.

## <a name="1-plan-for-skype-for-business"></a>1. Plan für Skype for Business

Wenn Sie **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** oder **Business Essentials** verwenden, können Sie Skype for Business für Onlineanrufe an andere Personen in Ihrem Unternehmen verwenden, die in Ihr Abonnement eingeschlossen sind. Wenn Ihr Unternehmen beispielsweise 10 Mitarbeiter hat, sind Sie in der Lage, [Skype for Business für Chats und Livekonferenzen zu nutzen](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) sowie mit [Skype for Business Besprechungen abzuhalten](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851), nachdem Sie die unten genannten Schritte 2 bis 6 ausgeführt haben. Sie können sogar eine [Skype for Business-Konferenz in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) einrichten.

Gehen Sie wie folgt vor, wenn Sie Skype for Business zum Tätigen und Annehmen von **Anrufen** von Personen *außerhalb* Ihres Unternehmens verwenden möchten:

- **Option 1. Verwenden Sie die kostenlose [Skype-App](https://www.skype.com/)**. Wenn Sie ein sehr kleines Unternehmen haben (zum Beispiel mit ein bis zwei Mitarbeitern), ist die Verwendung der Skype-App die bessere Lösung. Sie ist kostengünstiger für nationale und internationale Anrufe. Auch mit der Skype-App können Sie Telefonkonferenzen abhalten, Videoanrufe tätigen und Ihren Desktop für Präsentationen freigeben. [Überprüfen Sie die Zahlungssätze und -optionen](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Option 2. Wählen Sie ein Upgrade für Ihren Plan und kaufen Sie ein Telefonsystem und einen Anrufplan für Office 365**. Die einfachste Möglichkeit herauszufinden, wie viel dies kostet, und dann umzusteigen, besteht darin, den [Support für Business-Produkte zu kontaktieren – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b), damit dieser alles für Sie erledigt.

Weitere Informationen finden Sie unter [Planen des Setups von Office 365 für Unternehmen](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Anmelden bei Office 365
<a name="bkmk_signin"> </a>

Skype for Business Online ist Bestandteil der Office 365-Suite von Diensten. Um Skype for Business Online einzurichten, müssen Sie sich bei Office 365 anmelden. Gehen Sie dabei so vor:

1. Suchen Sie Ihre Office 365-Benutzer-ID (z. B.  <em>rob@fourthcoffee.com</em>  ). Sie haben vom Microsoft Online Services-Team eine E-Mail erhalten, die die Office 365-Benutzer-ID enthält, die Sie beim Erwerb von Skype for Business Online erstellt haben. Die E-Mail sieht in etwa so aus:

    ![Beispiel für die Willkommens-E-Mail, die Sie erhalten haben, nachdem Sie sich bei Skype for Business Online angemeldet haben. Sie enthält Ihre Office 365-Benutzer-ID.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Melden Sie sich beim [Admin Center](https://admin.microsoft.com) an, und geben Sie Ihre Office 365-Benutzer-ID und Ihr Kennwort ein. 

## <a name="3-set-up-your-domain-and-users"></a>3. Einrichten Ihrer Domäne und von Benutzern
<a name="bkmk_users"> </a>

Jetzt sind Sie bei Office 365 angemeldet und können Ihre Domäne und die Benutzer in Ihrer Organisation zur Verwendung von Skype for Business Online einrichten.

1. [Hinzufügen einer Domäne und von Benutzern zu Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Verwenden Sie den Office 365-Setup-Assistenten zum Einrichten Ihrer benutzerdefinierten Domäne (wie z. B. *fourthcoffee.com*) mit Office 365. Der **Office 365-Setup-Assistent beinhaltet standardmäßig das Einrichten von Skype for Business Online und das Erstellen Ihrer Skype for Business-Benutzer-IDs.** Sofern Sie den Assistenten bereits zum Einrichten Ihrer Domäne für Office 365 verwendet haben, ist dieser Schritt für Sie abgeschlossen.

2. [Domänen und DNS-Verbindungen überprüfen](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Vergewissern Sie sich mit unserem Tool für die Problembehandlung bei Domänen, dass Ihre Domänen- und DNS-Einstellungen richtig sind. Wenn Sie dies jetzt erledigen, können Sie später Einrichtungsprobleme leichter erkennen, da Sie DNS-Einstellungen als Quelle zukünftiger Probleme ausschließen können.

3. [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Die meisten Kleinunternehmen können diesen Schritt überspringen. **Wenn Ihr Zugriff auf das Internet jedoch durch eine Firewall oder einen Proxyserver eingeschränkt wird**, müssen Sie Regeln erstellen, die den Zugriff auf die Skype for Business Online-Endpunkte zulassen. Dieser fortgeschrittene Schritt wird am besten von einer Person ausgeführt, die sich mit dem Konfigurieren von Firewalls und Proxyservern auskennt. Wenn Sie damit keine Erfahrung haben, können Sie einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) beauftragen, Skype for Business für Sie einzurichten.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. Einrichten von Chats und Anwesenheitsinformationen in Ihrem Unternehmen
<a name="bkmk_IM"> </a>

Chatnachrichten und Anwesenheit ([Steuern des Zugriffs auf Ihre Anwesenheitsinformationen in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) sind grundlegende Funktionen in Skype for Business. Standardmäßig können Personen in Ihrem Unternehmen Skype und Chatnachrichten nutzen.

1. **Entscheiden Sie, mit wem Ihre Skype for Business-Benutzer kommunizieren können:**

   - [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](allow-users-to-contact-external-skype-for-business-users.md) Sie *und*  das andere Unternehmen müssen die Systeme konfigurieren.

     **WICHTIG**: Wenn Sie in Ihrem Unternehmen zwei Domänen verwenden, wie zum Beispiel in rob@contosowest.com und ina@contosoeast.com, müssen Sie diesen Schritt ausführen, damit alle Benutzer miteinander kommunizieren können.

   - [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) außerhalb Ihres Unternehmens

2. **Wählen Sie aus, wer sehen darf, ob Mitarbeiter online sind:** Die Funktion „Anwesenheitsinformationen" zeigt an, welche Person online ist, sowie deren Verfügbarkeit, wie „Verfügbar", „Beschäftigt", „Abwesend" oder „Hält Präsentation".

    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    Sie können für jede Person in Ihrem Unternehmen die Standardeinstellungen auswählen:

   - Die Onlinepräsenz einer Person automatisch allen Benutzern in der Organisation anzeigen

   - Die Onlinepräsenz einer Person nur ihren Kontakten anzeigen

Anweisungen hierzu finden Sie unter [Konfigurieren der Anwesenheitsinformationen in Skype for Business Online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. Herunterladen und Installieren von Skype for Business
<a name="bkmk_download"> </a>

Um Skype for Business auf Ihrem PC oder mobilen Gerät verwenden zu können, müssen Sie und alle Mitarbeiter in Ihrem Unternehmen zuerst den Skype for Business-Download auf ihren Geräten installieren.

- [Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Anweisungen zum Herunterladen der App aus dem Office 365-Portal und zum Installieren auf einem PC oder Mac.

- Den [Skype for Business-Client in Office 365](deploy-the-skype-for-business-client-in-office-365.md) bereitstellen: Anweisungen zum Bereitstellen der App in Großunternehmen.

- [Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Herunterladen und Installieren von sowie Anmelden bei Skype for Business auf Android-Geräten, iOS-Geräten und Windows-Telefonen.

- [Aus- oder Einschalten von Mobiltelefonbenachrichtigungen](turn-on-or-off-mobile-phone-notifications.md): Wenn Sie Skype for Business auf einem Mobilgerät installiert haben, können Sie und andere Personen in Ihrem Unternehmen Benachrichtigungen zu eingehenden und verpassten Sofortnachrichten erhalten.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. Test um sicherzustellen, dass alles funktioniert
<a name="bkmk_test"> </a>

Prüfen Sie zuerst, ob Sie und Ihre Kollegen sich bei [Video: An- und Abmelden bei Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451) können. Stellen Sie sicher, dass Sie Sofortnachrichten senden und empfangen können und gegenseitige Anwesenheitsinformationen verfügbar haben. Probieren Sie es mit einer Besprechung.

Probleme? Gehen Sie wie folgt vor:

- [Benötigen Sie Hilfe bei der Anmeldung bei Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) gängiger Anmeldeprobleme.

- [Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Wir helfen Ihnen gerne weiter!

## <a name="do-you-want-to-set-up-other-available-features"></a>Möchten Sie weitere verfügbare Features einrichten?
<a name="bkmk_more"> </a>

Vergewissern Sie sich vor dem Einrichten weiterer Features, dass Sie über die entsprechenden Lizenzen verfügen. [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen

Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation ist die Audiokonferenzfunktion in Skype for Business gedacht. Teilnehmer können sich mit einem Telefon in Skype for Business-Besprechungen einwählen, anstatt die Skype for Business-App auf einem Mobilgerät oder PC zu verwenden.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Einrichten des Telefonsystems und der Anrufpläne in Office 365

Mit der Telefonsystemfunktion in Office 365 erhalten Sie ein Telefonsystem für Ihr Unternehmen. Anrufe an andere Skype for Business-Benutzer in Ihrer Organisation sind kostenlos, und Ihre Mitarbeiter können Voicemail voneinander sowie von Anrufern von außen empfangen. Das bietet Ihnen das Telefonsystem-Add-On.

Wenn Sie den Anrufplandienst hinzufügen, erhalten Ihre Mitarbeiter eine primäre Telefonnummer in Skype for Business. Sie können Telefonanrufe außerhalb des Unternehmens tätigen und empfangen. Außerdem können sie Sprachanrufe über VoIP-Telefone, PCs und mobile Geräte tätigen. Und bei Notfällen können sie die Notrufnummern anrufen.

Eine schrittweise Anleitung finden Sie unter „Einrichten von Anrufplänen".

### <a name="set-up-skype-meeting-broadcast"></a>Einrichten einer Skype-Livekonferenz

Skype-Livekonferenz ist eine Funktion, mit der Sie Besprechungen mit bis zu 10.000 Teilnehmern erstellen, hosten und live abhalten können. **Weitere Informationen zur Funktionsweise finden Sie unter [Was ist eine Skype-Livekonferenz?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**.

Hier ist eine Übersicht über die Schritte zum Einrichten von Skype-Livekonferenz:

1. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Weisen Sie allen Personen, die Livekonferenzen **hosten** werden, Lizenzen für **Skype for Business Online** oder einen **Enterprise-Plan** zu.

2. [Aktivieren von Skype-Livekonferenz](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): Diese Funktion ist standardmäßig deaktiviert. Nachdem Sie diese Funktion aktiviert haben, können Ihre Benutzer Livekonferenzen mit anderen Personen in Ihrem Unternehmen hosten.

3. [Einrichten Ihres Netzwerks für Skype-Livekonferenz](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): Wenn Sie Webinare und andere Livekonferenzen mit Teilnehmern außerhalb Ihrer Organisation hosten möchten, müssen Sie Ihr Netzwerk konfigurieren.

4. [Planen einer Skype-Livekonferenz](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) und [Teilnehmen an einer Skype-Livekonferenz](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Sie können diese Funktionen überprüfen, indem Sie eine Skype-Livekonferenz auf *https://portal.broadcast.skype.com* planen und ein Benutzer anschließend versucht, an der Konferenz teilzunehmen.

## <a name="learn-about-network-connectivity-requirements"></a>Informationen zu den Anforderungen an die Netzwerkverbindung
<a name="bkmk_more"> </a>

Die Qualität der End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Audio, Video und Anwendungsfreigabe in Skype for Business. Optimale Ergebnisse erzielen Sie, indem Sie für eine hohe Verbindungsqualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online sorgen. Informationen zu Netzwerken und zur Optimierung finden Sie unter [Optimieren von Skype for Business Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>Haben Sie alle Komponenten eingerichtet? Erste Schritte mit Skype for Business
<a name="bkmk_more"> </a>

[Skype for Business-Schulung](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Schauen Sie sich diese Liste mit Schulungsthemen an, die Ihnen bei den ersten Schritten helfen, damit Sie umgehend loslegen können!

[Starten eines Skype for Business-Konferenzanrufs](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Festlegen von Videogerätoptionen in Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Tätigen und Annehmen eines Videoanrufs mit Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Verwandte Themen
<a name="bkmk_more"> </a>

[Planen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=400791)



