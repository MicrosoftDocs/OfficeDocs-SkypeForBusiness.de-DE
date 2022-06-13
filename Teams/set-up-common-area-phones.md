---
title: Einrichten der Lizenz für den gemeinsamen Bereich Telefon
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
description: 'Erfahren Sie, wie Sie Telefone für gemeinsame Bereiche für Lobbys, Empfangsbereiche und Konferenzräume einrichten. '
ms.openlocfilehash: f3f3ee2c98e48a41bb12dcaa7fc461c623f49994
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045824"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Bereitstellen von Telefonen für gemeinsame Bereiche für Microsoft Teams

Ein Telefon im einheitlichen Bereich befindet sich in der Regel in einem Bereich wie einer Lobby oder einem anderen Bereich, der vielen Personen zur Verfügung steht, um einen Anruf zu tätigen. z. B. ein Empfangsbereich, eine Lobby oder ein Konferenztelefon. Telefone für gemeinsame Bereiche sind mit Konten angemeldet, die an eine Lizenz für den gemeinsamen Bereich Telefon gebunden sind.

Dieser Artikel enthält eine Übersicht darüber, wie Sie Teams Telefone als Telefone für gemeinsame Bereiche für gemeinsame Räume bereitstellen und konfigurieren. Für eine umfassendere Besprechungsraumerfahrung, einschließlich Audiokonferenzen, sollten Sie die dedizierte Besprechungsraum-Lizenz mit einem Besprechungsraumgerät erwerben.

## <a name="overview"></a>Übersicht

Die Lizenz für den gemeinsamen Bereich Telefon unterstützt:

|                                           | Telefon für gemeinsame Bereiche                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Telefon** &sup1;                   | &#x2714;                                          |
| **Audiokonferenzen**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium Plan 1** | &#x2714;                                          |
| **Exchange Online Plan 2**                | &#x2714;  &sup3;                                  |
| **Weltweite Verfügbarkeit**                | &#x2714;                                          |
| **Kanalverfügbarkeit**                  | EA, EAS, EES, CSP, Web Direct, GCC, GCC-High, DoD |

&sup1; Früher als Telefonsystem bekannt.

&sup2; Telefone für gemeinsame Bereiche können über eine vom Besprechungsorganisator bereitgestellte Einwahlnummer an Audiokonferenzen teilnehmen.  

&sup3; Nur cloudbasierte Voicemailfunktionen.

>[!NOTE]
> Konten für Telefone im einheitlichen Bereich, die in Skype for Business Server erstellt wurden, können nicht zu Microsoft Teams migriert werden. Führen Sie die Schritte in diesem Artikel aus, um diese Konten für Teams neu zu erstellen und bei Bedarf Ihre PTSN-Konnektivität zu migrieren.

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

Zuerst müssen Sie eine Common Area Telefon (CAP)-Lizenz erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen. Um nach zertifizierten Telefonen zu suchen und mehr zu erfahren, wechseln Sie zu [Microsoft Teams Geräten](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Wechseln Sie in der Microsoft 365 Admin Center zu **"****Abrechnungskaufdienste** > ". 

2. Wenn der Abschnitt **"Ansicht nach Kategorie** " noch nicht angezeigt wird, wechseln **Sie zu "Von Microsoft kaufen**", und wählen Sie **"Produkte anzeigen"** aus. Wählen Sie dann **"Zusammenarbeit und Kommunikation**" aus.  

3. Suchen Sie in der Produktliste **nach Telefon "Gemeinsamer Bereich**", und wählen Sie **"Details**" aus.

4. Geben Sie die Anzahl der benötigten Lizenzen ein, und wählen Sie **"Kaufen"** aus.

>[!NOTE]
>Wenn Sie Intune in Ihrer Umgebung verwenden und über Regeln für bedingten Zugriff verfügen, die die Gerätekompatibilität erfordern, müssen Sie dem Gerätekonto für das Telefon mit gemeinsamem Bereich eine Azure Active Directory Premium Plan 1 und Intune Lizenz zuweisen.
>
>Telefone für gemeinsame Bereiche können durch Regeln für bedingten Zugriff und andere Identitätskonfigurationen wie die mehrstufige Authentifizierung beeinträchtigt werden. Weitere Informationen finden Sie unter ["Bewährte Methoden für die Authentifizierung für Teams Android Geräte](devices/authentication-best-practices-for-android-devices.md)".

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Schritt 2: Erstellen eines neuen Benutzerkontos und Zuweisen von Lizenzen

### <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Wenn Sie mehrere Telefone für gemeinsame Bereiche gleichzeitig bereitstellen, erfahren Sie, wie Sie Konten erstellen und [Lizenzen mithilfe von PowerShell](#using-powershell) zuweisen.

Wenn Sie ein Gerät bereitstellen:

1. Wechseln Sie in der Microsoft 365 Admin Center zu **"Aktive Benutzer** > **benutzer** > **hinzufügen"**.

2. Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.

3. Geben Sie einen Anzeigenamen ein, wenn dieser nicht automatisch wie "Hauptempfang" generiert wird.

4. Geben Sie einen Benutzernamen wie "MainReception" oder "Mainlobby" ein.

5. Legen Sie das Kennwort für Ihr Telefon im einheitlichen Bereich manuell fest, um dies zu verhindern. Deaktivieren Sie dazu das Kontrollkästchen **"Kennwort automatisch erstellen** ", und **fordern Sie diesen Benutzer auf, sein Kennwort bei der ersten Anmeldung zu ändern**.  

    >[!Important]
    > Das manuelle Festlegen eines Kennworts für Telefone in allgemeinen Bereichen wird dringend empfohlen, um Anmeldeprobleme für Ihre Endbenutzer zu vermeiden.

6. Wählen Sie den Verwendungsort des Geräts aus, und weisen Sie dem Konto die Lizenz für den gemeinsamen Bereich Telefon zu. Wenn andere Lizenzen benötigt werden, z. B. Anrufpläne, weisen Sie sie zu.

>[!NOTE]
> Sie müssen keine Telefonsystem Lizenz hinzufügen. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.
>
>Wenn Sie Microsoft-Telefon System Direct Routing oder Telefonieanbieter nicht verwenden, können Sie Lizenzen für Anrufpläne hinzufügen. Weitere Informationen zu Lizenzen finden Sie [unter Microsoft Teams Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, wenn Sie Lizenzen für mehrere Benutzerkonto gleichzeitig erstellen und zuweisen möchten. Weitere Informationen finden [Sie unter Erstellen Microsoft 365 Benutzerkonten mit PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) und [Zuweisen Microsoft 365 Lizenzen zu Benutzerkonten mit PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Schritt 3: Festlegen von Richtlinien für Telefone für gemeinsame Bereiche

Verwenden Sie Richtlinien, um zu steuern, welche Features Benutzern auf Telefonen in einheitlichen Bereichen zur Verfügung stehen.

>[!NOTE]
>Nachdem Sie eine Richtlinie zugewiesen haben, melden Sie sich vom Telefon ab und wieder an. Es kann bis zu einer Stunde dauern, bis eine Richtlinienzuweisung wirksam wird.

### <a name="ip-phone-policies"></a>IP-Telefonrichtlinien

Bei Telefonen, die mit Konten angemeldet sind, denen eine Lizenz für den gemeinsamen Bereich Telefon zugewiesen wurde, wird die Benutzeroberfläche des einheitlichen Bereichs angezeigt.

Wenn Sie die Standardschnittstelle eines Telefons überschreiben möchten, sollten Sie eine [IP-Telefonrichtlinie](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true) erstellen. Wenn z. B. ein Telefon im öffentlichen Bereich verwendet wird, legen Sie eine IP-Telefonrichtlinie fest, um die Suche im globalen Adressbuch Ihrer Organisation einzuschränken und hot-desking zu blockieren.For example, if a common area phone is used in a public area, set an IP phone policy to restrict searching your organization's Global Address Book and block hot-desking. Weitere Informationen finden [Sie unter "Festlegen Teams Android Geräte-Benutzeroberfläche](devices/Teams-Android-devices-user-interface.md)".

### <a name="calling-policies"></a>Anrufpläne

Verwenden Sie Anrufrichtlinien, um private Anrufe, Anrufweiterleitung oder gleichzeitiges Anrufen auf Telefonen im einheitlichen Bereich zu aktivieren. Weitere Informationen finden Sie [unter Anrufen und Anrufweiterleitung in Teams](teams-calling-policy.md).

Standardmäßig ist das Parken von Anrufen für Telefone in allgemeinen Bereichen nicht aktiviert. Sie müssen eine Richtlinie erstellen, um sie zu aktivieren. Weitere Informationen finden Sie [unter "Parken von Anrufen" und "Abrufen in Microsoft Teams](call-park-and-retrieve.md)".

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Schritt 4 – Erwerben und Zuweisen von Telefonnummern

Informationen zum Erwerben und Zuweisen von Telefonnummern basierend auf Ihrer PSTN-Konnektivitätsoption finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md) .

## <a name="step-5---sign-in"></a>Schritt 5 – Anmelden

Nachdem Sie ein Benutzerkonto erstellt und konfiguriert haben, können Sie sich bei einem Telefon anmelden. Je nachdem, wie viele Telefone Sie bereitstellen, haben Sie drei Anmeldeoptionen:

- [Lokale Anmeldung](#local-sign-in)
- [Anmelden von einem anderen Gerät aus](#sign-in-from-another-device)
- [Anmelden mit dem Teams Admin Center](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Lokale Anmeldung

So melden Sie sich lokal mit einem Benutzernamen und Kennwort an: 

1. Aktivieren des Telefons für gemeinsame Bereiche

2. Wählen Sie **"Auf diesem Gerät anmelden"** aus.

3. Folgen Sie den Anmeldehinweisen auf dem Gerät. Nach der Anmeldung zeigt das Telefon die Benutzeroberfläche des Telefons für gemeinsame Bereiche an.

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Setuprichtlinie verwenden, mit der die aufrufende App gelöst wird, wird die Wähltastatur nicht im Telefon für den gemeinsamen Bereich angezeigt. Weitere Informationen zu Teams Setuprichtlinien finden [Sie unter Verwalten von App-Setuprichtlinien in Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Anmelden von einem anderen Gerät aus

Sie können sich auch mithilfe eines Codes von einem anderen Gerät aus bei einem Telefon im einheitlichen Bereich anmelden. Wenn Sie sich auf diese Weise anmelden, geben Sie den Benutzernamen und das Kennwort auf einem anderen Gerät und nicht auf dem Telefon selbst ein.

1. Suchen Sie zunächst auf Ihrem Telefon im einheitlichen Bereich nach dem Code, der auf dem Anmeldebildschirm angezeigt wird.

2. Wechseln Sie auf einem anderen Gerät zu https://www.microsoft.com/devicelogin.

3. Geben Sie den Code ein, und folgen Sie den Anweisungen, um die Anmeldung abzuschließen.

### <a name="sign-in-using-the-teams-admin-center"></a>Anmelden mit dem Teams Admin Center

Als Administrator können Sie Telefone für gemeinsame Bereiche über das Teams Admin Center remote bereitstellen und anmelden. Dies ist die effizienteste Anmeldemethode, wenn Sie eine große Anzahl von Telefonen gleichzeitig bereitstellen. Weitere Informationen finden Sie [unter Remotebereitstellung und Anmelden für Teams Android Geräte](devices/remote-provision-remote-login.md).

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie nun Telefone für gemeinsame Bereiche für Ihre Organisation eingerichtet und angemeldet haben, können Sie sie im Teams Admin Center verwalten. Weitere Informationen [finden Sie unter Microsoft Teams: Verwalten Ihrer Geräte](devices/device-management.md).

## <a name="related-topics"></a>Verwandte Themen

- [Remoteaktualisierung Microsoft Teams Geräten](devices/remote-update.md)
- [Verwalten Microsoft Teams Gerätetags](devices/manage-device-tags.md)
- [Microsoft Teams der Geräteintegritätsüberwachung](alerts/device-health-status.md)
