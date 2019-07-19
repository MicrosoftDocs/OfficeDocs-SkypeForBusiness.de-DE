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
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: 'Erfahren Sie, wie Sie Ihre Domäne, Benutzer, Chat-und Anwesenheitsinformationen für Ihre Organisation einrichten, um Skype for Business zu installieren. Sehen Sie sich auch an, wie Sie Audiokonferenz-, Telefon System-und Anrufpläne sowie Skype-Live Konferenz einrichten. '
ms.openlocfilehash: 239e1c39563594ffe1ff106284bbbf912367fb88
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792620"
---
# <a name="set-up-skype-for-business-online"></a>Einrichten von Skype for Business Online

Sie müssen über die Berechtigungen eines globalen Administrator für Office 365 verfügen, um Skype for Business einzurichten. Wenn der Zugriff auf das Internet jedoch durch eine Firewall oder einen Proxyserver eingeschränkt wird, können Sie einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) zur Einrichtung von Skype for Business heranziehen.

## <a name="setting-up-skype"></a>Einrichten von Skype

Sie benötigen Hilfe beim Einrichten von Skype im Rahmen Ihres Office 365-Abonnements? In diesem Artikel finden Sie die Schritte, die Sie dazu ausführen müssen.

## <a name="1-plan-for-skype-for-business"></a>1. Planen für Skype for Business

Wenn Sie **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** oder **Business Essentials** verwenden, können Sie Skype for Business für Onlineanrufe an andere Personen in Ihrem Unternehmen verwenden, die in Ihr Abonnement eingeschlossen sind. Wenn Ihr Unternehmen beispielsweise 10 Personen umfasst, können Sie mit der [Verwendung von Skype for Business für Chats und Onlinebesprechungen](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) und Besprechungen [mit Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) über Skype for Business beginnen, nachdem Sie die Schritte 2-6 unten ausgeführt haben. Und Sie können auch [eine Skype for Business-Besprechung in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) für Onlinebesprechungen einrichten!

Gehen Sie wie folgt vor, wenn Sie Skype for Business zum Tätigen und Annehmen von **Anrufen** von Personen *außerhalb*  Ihres Unternehmens verwenden möchten:

- **Option 1. Verwenden Sie die kostenlose [Skype-App](https://www.skype.com/)**. Wenn Sie ein sehr kleines Unternehmen haben (zum Beispiel mit ein bis zwei Mitarbeitern), ist die Verwendung der Skype-App die bessere Lösung. Sie ist für Inlands- und Auslandsanrufe kostengünstiger. Sie können weiterhin Konferenzgespräche führen, Videoanrufe tätigen und Ihren Desktop für Präsentationen freigeben. [Überprüfen Sie die Zahlungssätze und -optionen](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Option 2. Aktualisieren Sie Ihren Plan, und kaufen Sie das Telefon System und einen Anrufplan für Office 365**. Die einfachste Methode, um herauszufinden, wie viel dies kostet, und dann den Schalter zu setzen, besteht darin, den [Support für Business-Produkte zu kontaktieren – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) , damit Sie alles für Sie erledigen können.

Weitere Informationen finden Sie unter [Planen des Setups von Office 365 for Business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Anmelden bei Office 365
<a name="bkmk_signin"> </a>

Skype for Business Online ist Bestandteil der Office 365-Suite von Diensten. Um Skype for Business Online einzurichten, müssen Sie sich bei Office 365 anmelden. Gehen Sie dabei so vor:

1. Suchen Sie Ihre Office 365-Benutzer-ID (z. B.  <em>rob@fourthcoffee.com</em>  ). Sie haben vom Microsoft Online Services-Team eine E-Mail erhalten, die die Office 365-Benutzer-ID enthält, die Sie beim Erwerb von Skype for Business Online erstellt haben. Die E-Mail sieht in etwa so aus:

    ![Beispiel für die Willkommens-E-Mail, die Sie erhalten haben, nachdem Sie sich bei Skype for Business Online angemeldet haben. Sie enthält Ihre Office 365-Benutzer-ID.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Melden Sie sich beim Admin Center an, und geben Sie Ihre Office 365-Benutzer-ID und Ihr Kennwort ein. Nachdem Sie sich angemeldet haben, wird das Microsoft 365 Admin Center angezeigt:

    ![Ein Beispiel für das Aussehen des Admin Centers, wenn Sie über einen Skype for Business Online-Plan verfügen.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. Einrichten der Domäne und der Benutzer
<a name="bkmk_users"> </a>

Jetzt sind Sie bei Office 365 angemeldet und können Ihre Domäne und die Benutzer in Ihrer Organisation zur Verwendung von Skype for Business Online einrichten.

1. [Hinzufügen einer Domäne und von Benutzern zu Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Verwenden Sie den Office 365-Setup-Assistenten, um Ihre benutzerdefinierte Domäne (beispielsweise *fourthcoffee.com*) mit Office 365 einzurichten. **Standardmäßig umfasst der Office 365-Setup-Assistent das Einrichten von Skype for Business Online und das Erstellen Ihrer Skype for Business-Benutzer-IDs.** Wenn Sie den Assistenten bereits zum Einrichten Ihrer Domäne für Office 365 verwendet haben, haben Sie diesen Schritt abgeschlossen.

2. [Domänen- und DNS-Verbindungen überprüfen](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Vergewissern Sie sich mit unserem Tool für die Problembehandlung bei Domänen, dass Ihre Domänen- und DNS-Einstellungen richtig sind. Wenn Sie dies jetzt erledigen, können Sie später Einrichtungsprobleme leichter erkennen, da Sie DNS-Einstellungen als Quelle zukünftiger Probleme ausschließen können.

3. [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Die meisten Kleinunternehmen können diesen Schritt überspringen. **Wenn Ihr Zugriff auf das Internet jedoch durch eine Firewall oder einen Proxyserver eingeschränkt wird**, müssen Sie Regeln erstellen, die den Zugriff auf die Skype for Business Online-Endpunkte zulassen. Dieser fortgeschrittene Schritt wird am besten von einer Person ausgeführt, die sich mit dem Konfigurieren von Firewalls und Proxyservern auskennt. Wenn Sie dies noch nicht getan haben, sollten Sie einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) einstellen, um Skype for Business für Sie einzurichten.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. Einrichten von Sofortnachrichten und Anwesenheitsinformationen in Ihrer Organisation
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

Anweisungen hierzu finden Sie unter [Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. Herunterladen und Installieren von Skype for Business
<a name="bkmk_download"> </a>

Um Skype for Business auf Ihrem PC oder mobilen Gerät verwenden zu können, müssen Sie und alle Mitarbeiter in Ihrem Unternehmen zuerst den Skype for Business-Download auf ihren Geräten installieren.

- [Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Anweisungen zum Herunterladen der App aus dem Office 365-Portal und zum Installieren auf einem PC oder Mac.

- [Bereitstellen des Skype for Business-Clients in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Anweisungen zum Bereitstellen der app in einem Großunternehmen.

- [Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Herunterladen und Installieren von Skype for Business auf Android-Geräten, iOS-Geräten und Windows Phone-Geräten sowie Anmelden.

- [Aktivieren oder Deaktivieren von Benachrichtigungen über Mobiltelefone](turn-on-or-off-mobile-phone-notifications.md): Wenn Sie Skype for Business auf einem mobilen Gerät installiert haben, können Sie und andere Personen in Ihrem Unternehmen Benachrichtigungen über eingehende und verpasste Sofortnachrichten erhalten.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. Testen der Funktionen
<a name="bkmk_test"> </a>

Prüfen Sie zuerst, ob Sie und Ihre Kollegen sich bei [Video: An- und Abmelden bei Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451) können. Stellen Sie sicher, dass Sie Sofortnachrichten senden und empfangen können und gegenseitige Anwesenheitsinformationen verfügbar haben. Probieren Sie es mit einer Besprechung.

Probleme? Gehen Sie wie folgt vor:

- [Benötigen Sie Hilfe bei der Anmeldung bei Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) gängiger Anmeldeprobleme.

- [Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Wir helfen Ihnen gerne weiter!

## <a name="do-you-want-to-set-up-other-available-features"></a>Möchten Sie andere verfügbare Features einrichten?
<a name="bkmk_more"> </a>

Vergewissern Sie sich vor dem Einrichten weiterer Features, dass Sie über die entsprechenden Lizenzen verfügen. [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen

Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation ist die Audiokonferenzfunktion in Skype for Business gedacht. Teilnehmer können sich mit einem Telefon in Skype for Business-Besprechungen einwählen, anstatt die Skype for Business-App auf einem Mobilgerät oder PC zu verwenden.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Einrichten des Telefonsystems und der Anrufpläne in Office 365

Mit der Telefonsystemfunktion in Office 365 erhalten Sie ein Telefonsystem für Ihr Unternehmen. Anrufe an andere Skype for Business-Benutzer in Ihrer Organisation sind kostenlos, und Ihre Mitarbeiter können Voicemail voneinander sowie von Anrufern von außen empfangen. Das bietet Ihnen das Telefonsystem-Add-On.

Wenn Sie den Anrufplandienst hinzufügen, erhalten Ihre Mitarbeiter eine primäre Telefonnummer in Skype for Business. Sie können Telefonanrufe außerhalb des Unternehmens tätigen und empfangen. Außerdem können sie Sprachanrufe über VoIP-Telefone, PCs und mobile Geräte tätigen. Und bei Notfällen können sie die Notrufnummern anrufen.

Eine schrittweise Anleitung finden Sie unter „Einrichten von Anrufplänen".

### <a name="set-up-skype-meeting-broadcast"></a>Einrichten Skype-Livekonferenz

Skype-Livekonferenz ist eine Funktion, mit der Sie Besprechungen mit bis zu 10.000 Teilnehmern erstellen, hosten und live abhalten können. **Weitere Informationen zur Funktionsweise finden Sie unter [Was ist eine Skype-Livekonferenz?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**.

Hier ist eine Übersicht über die Schritte zum Einrichten von Skype-Livekonferenz:

1. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Weisen Sie allen Personen, die Livekonferenzen **hosten** werden, Lizenzen für **Skype for Business Online** oder einen **Enterprise-Plan** zu.

2. [Skype-Live Konferenz aktivieren](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): dieses Feature ist standardmäßig nicht aktiviert. Wenn Sie sie aktivieren, können Ihre Benutzer Livekonferenzen mit anderen Personen in Ihrer Organisation hosten.

3. [Einrichten Ihres Netzwerks für Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)-Live Konferenz: Wenn Sie Webinare und andere Broadcasts mit Teilnehmern außerhalb Ihrer Organisation hosten möchten, müssen Sie Ihr Netzwerk konfigurieren.

4. [Planen einer Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) -Live Konferenz und [teilnehmen an einer Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)-Live Konferenz: Stellen Sie sicher, dass Broadcast-Besprechungen funktionieren *https://portal.broadcast.skype.com* , indem Sie eine Skype-Live Konferenz planen und dann versuchen, an der Besprechung teilzunehmen.

## <a name="learn-about-network-connectivity-requirements"></a>Erfahren Sie mehr über Anforderungen an die Netzwerkkonnektivität
<a name="bkmk_more"> </a>

Die Qualität der End-to-End-Netzwerkkonnektivität hat großen Einfluss auf die Qualität von Audio, Video und Anwendungsfreigabe in Skype for Business. Optimale Ergebnisse erzielen Sie, indem Sie für eine hohe Verbindungsqualität zwischen Ihrem Unternehmensnetzwerk und Skype for Business Online sorgen. Informationen zu Netzwerken und zur Optimierung finden Sie unter [Optimieren von Skype for Business Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>Haben Sie die Einrichtung abgeschlossen? Erste Schritte mit Skype for Business
<a name="bkmk_more"> </a>

[Skype for Business-Schulung](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Schauen Sie sich diese Liste mit Schulungsthemen an, damit Sie schnell loslegen können!

[Starten einer Skype for Business-Telefonkonferenz](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Festlegen von Videogerätoptionen in Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Tätigen und Annehmen eines Videoanrufs mit Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Verwandte Themen
<a name="bkmk_more"> </a>

[Planen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=400791)



