---
title: Einrichten der gemeinsamen Telefon-Lizenz
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie Telefone im allgemeinen Bereich für Lobbys, Empfangsbereiche und Konferenzräume einrichten. '
ms.openlocfilehash: a4e4720fe7baf58d0da6f00800c61b706ec48516
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279263"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Bereitstellen häufig verwendeter Telefone für Microsoft Teams

Ein Telefon in der Nähe eines Telefons befindet sich normalerweise in einem Bereich wie einem Wartebereich oder einem anderen Bereich, der für viele Personen zum Anrufen zur Verfügung steht. z. B. einen Empfangsbereich, einen Wartebereich oder ein Konferenztelefon. Telefone in gängigen Gegenden sind mit Konten angemeldet, die mit einer gemeinsamen Telefon sind.

Dieser Artikel bietet eine Übersicht über das Bereitstellen und Konfigurieren Teams Telefonen als allgemeine Telefone in der Nähe für gemeinsam genutzte Bereiche. Für eine vollständigere Besprechungsraumerfahrung, einschließlich Audiokonferenzen, sollten Sie die dedizierte Lizenz Besprechungsraum einem Besprechungsraumgerät erwerben.

## <a name="overview"></a>Übersicht

Der gemeinsame Bereich, Telefon von der Lizenz unterstützt wird: 


| &nbsp;  |  Telefon für gemeinsame Bereiche  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Telefonsystem |    &#x2714; |
|Audiokonferenzen |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Weltweite Verfügbarkeit |       &#x2718; &sup2;  |
|Verfügbarkeit von Kanälen |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Telefone vor Ort können über die vom Besprechungsorganisator bereitgestellte Einwahlnummer an Audiokonferenzen teilnehmen.

&sup2; In souveränen Wolken nicht verfügbar  

>[!NOTE]
> Konten für Telefone in gängigen Skype for Business Server können nicht zu Microsoft Teams. Führen Sie die Schritte in diesem Artikel aus, um diese Konten für die Teams neu zu erstellen und, falls erforderlich, Ihre PTSN-Verbindung zu migrieren.

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

Zuerst müssen Sie eine Cap-Lizenz (Common Area Telefon) erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen. Weitere Informationen zu zertifizierten Telefonen finden Sie unter Microsoft Teams [Geräte](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Wechseln Sie Microsoft 365 Admin Center Dienste **zur** **AbrechnungPurchase** > . 

2. Wenn der **Abschnitt Nach Kategorie** anzeigen noch nicht angezeigt wird, wechseln Sie zu Von **Microsoft** kaufen, und wählen Sie **Produkte anzeigen aus**. Wählen Sie dann **Zusammenarbeit und Kommunikation aus**.  

3. Suchen Sie in der Produktliste nach **gemeinsamem Telefon** und wählen Sie **Details aus**.

4. Geben Sie die Anzahl der benötigten Lizenzen ein, und wählen Sie **Kaufen aus**.

>[!NOTE]
>Wenn Sie Intune in Ihrer Umgebung verwenden und über bedingte Zugriffsregeln verfügen, die Gerätekonformität erfordern, müssen Sie dem Gerätekonto für das gemeinsame Telefon eine Azure Active Directory Premium Plan 1- und Intune-Lizenz zuweisen.
>
>Telefone in gängigen Bereich können durch Regeln für bedingten Zugriff und andere Identitätskonfigurationen wie die mehrstufige Authentifizierung betroffen sein. Weitere [Informationen finden Sie unter Bewährte Methoden für Teams für Android-Geräte](devices/authentication-best-practices-for-android-devices.md).

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Schritt 2: Erstellen eines neuen Benutzerkontos und Zuweisen von Lizenzen

### <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Wenn Sie mehrere Smartphones in einem allgemeinen Bereich gleichzeitig bereitstellen, erfahren Sie hier, wie Sie mithilfe von [PowerShell](#using-powershell) Konten erstellen und Lizenzen zuweisen.

Wenn Sie ein Gerät bereitstellen:

1. Wechseln Sie Microsoft 365 Admin Center **Zu BenutzerAktive** >  **BenutzerHinzufügen** >  **eines Benutzers**.

2. Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.

3. Geben Sie einen Anzeigenamen ein, wenn dieser nicht automatisch generiert wird, z. B. "Hauptaufnahme".

4. Geben Sie einen Benutzernamen wie "Main Vorname" oder "Mainlobby" ein.

5. Legen Sie das Kennwort für Ihr häufig verwendetes Telefon in Der Nähe manuell so ein, dass dies verhindert wird. Deaktivieren Sie dazu Automatisch **ein Kennwort erstellen** und fordern Sie den Benutzer auf, sein Kennwort bei der ersten Anmeldung **zu ändern**.  

    >[!Important]
    > Das manuelle Festlegen eines Kennworts für Allgemeine Telefone in der Nähe wird dringend empfohlen, um Anmeldeprobleme für Ihre Endbenutzer zu vermeiden.

6. Wählen Sie den Verwendungsstandort des Geräts aus, und weisen Sie dem Telefon den gemeinsamen Bereich zu. Wenn andere Lizenzen erforderlich sind, z. B. Anrufpläne, weisen Sie diese zu.

>[!NOTE]
> Sie müssen keine Lizenz Telefonsystem hinzufügen. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.
>
>Wenn Sie keine Anrufplanlizenzen Microsoft-Telefon System Direct Routing oder Operator Verbinden, können Sie Anrufpläne-Lizenzen hinzufügen. Weitere Informationen zu Lizenzen finden Sie unter [Microsoft Teams Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, wenn Sie Lizenzen für mehrere Benutzerkonten gleichzeitig erstellen und zuweisen möchten. Weitere Informationen Microsoft 365 Sie unter Erstellen von Microsoft 365 mit [PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) und Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten mit [PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide).

## <a name="step-3---set-policies-for-common-area-phones"></a>Schritt 3 – Festlegen von Richtlinien für Telefone im allgemeinen Bereich

Mithilfe von Richtlinien können Sie steuern, welche Features für Benutzer auf Telefonen in gängigen Bereich zur Verfügung stehen.

>[!NOTE]
>Nachdem Sie eine Richtlinie zugewiesen haben, melden Sie sich beim Telefon ab und wieder an. Es kann bis zu einer Stunde dauern, bis eine Richtlinienzuweisung wirksam wird.

### <a name="ip-phone-policies"></a>IP-Telefonrichtlinien

Bei Telefonen, die mit Konten angemeldet sind, denen eine gemeinsame Telefon zugewiesen wurde, wird die benutzerfreundliche Umgebung des gemeinsamen Bereichs angezeigt.

Wenn Sie die Standardschnittstelle eines Smartphones überschreiben möchten, sollten Sie eine [IP-Telefonrichtlinie erstellen](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). Wenn beispielsweise ein telefonübliches Telefon in einem öffentlichen Bereich verwendet wird, legen Sie eine IP-Telefonrichtlinie zum Einschränken der Suche im globalen Adressbuch Ihrer Organisation und zum Blockieren von Hot-King-Adressen für ihr Unternehmen auf. Weitere [Informationen Teams Sie unter Festlegen der Benutzeroberfläche für](devices/Teams-Android-devices-user-interface.md) Android-Geräte.

### <a name="calling-policies"></a>Anrufpläne

Verwenden Sie Anrufrichtlinien, um private Anrufe zu ermöglichen, indem Sie Anruf weiterleiten oder gleichzeitig auf Telefonen in der Nähe anrufen. Weitere [Informationen finden Sie unter](teams-calling-policy.md) Anrufe und Teams in einer Telefonkonferenz.

Das Parken von Anrufen ist für Telefone in der nähe der Nähe standardmäßig nicht aktiviert. Sie müssen eine Richtlinie erstellen, um sie zu aktivieren. Weitere [Informationen finden Sie unter Microsoft Teams](call-park-and-retrieve.md) Parken und Abrufen von Anrufen.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Schritt 4 – Erwerben und Zuweisen von Telefonnummern

Informationen [zum Erwerben und Zuweisen von](manage-phone-numbers-landing-page.md) Telefonnummern basierend auf Ihrer PSTN-Konnektivitätsoption finden Sie unter Verwalten von Telefonnummern für Ihre Organisation.

## <a name="step-5---sign-in"></a>Schritt 5 – Anmelden

Nachdem Sie ein Benutzerkonto erstellt und konfiguriert haben, können Sie sich bei einem Smartphone anmelden. Je nachdem, wie viele Telefone Sie bereitstellen, haben Sie drei Anmeldeoptionen:

- [Lokale Anmeldung](#local-sign-in)
- [Anmelden von einem anderen Gerät aus](#sign-in-from-another-device)
- [Anmelden über das Teams Admin Center](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Lokale Anmeldung

So melden Sie sich lokal mit einem Benutzernamen und Kennwort an: 

1. Aktivieren des Telefons in der Nähe

2. Wählen **Sie Auf diesem Gerät anmelden aus.**

3. Folgen Sie den Anmeldebeschreibungen auf dem Gerät. Sobald Sie angemeldet sind, wird auf dem Telefon die gemeinsame Benutzererfahrung des Telefons angezeigt.

### <a name="sign-in-from-another-device"></a>Anmelden von einem anderen Gerät aus

Sie können sich auch mit einem Code von einem anderen Gerät aus bei einem gemeinsamen Telefon vor Ort anmelden. Wenn Sie sich auf diese Weise anmelden, geben Sie den Benutzernamen und das Kennwort auf einem anderen Gerät und nicht auf dem Smartphone selbst ein.

1. Suchen Sie zunächst auf Dem Handy in der Nähe nach dem Code, der auf dem Anmeldebildschirm angezeigt wird.

2. Wechseln Sie auf einem anderen Gerät zu https://www.microsoft.com/devicelogin.

3. Geben Sie den Code ein, und folgen Sie den Anweisungen zum Abschließen der Anmeldung.

### <a name="sign-in-using-the-teams-admin-center"></a>Anmelden über das Teams Admin Center

Als Administrator können Sie telefonieren und sich remote über das Admin Center Teams anmelden. Dies ist die effizienteste Anmeldemethode, wenn Sie eine große Anzahl von Telefonen gleichzeitig bereitstellen. Weitere [Informationen finden Sie unter Remotebereitstellung und -Teams für Android-Geräte](devices/remote-provision-remote-login.md).

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Telefone in einem gemeinsamen Bereich für Ihre Organisation eingerichtet und angemeldet haben, können Sie diese im Teams Admin Center verwalten. Weitere [Microsoft Teams finden Sie](devices/device-management.md) unter Verwalten Ihrer Geräte.

## <a name="related-topics"></a>Verwandte Themen

- [Remoteaktualisierung Microsoft Teams Geräte](devices/remote-update.md)
- [Verwalten Microsoft Teams Von Gerätetags](devices/manage-device-tags.md)
- [Microsoft Teams der Geräteinte health-Überwachung](alerts/device-health-status.md)
