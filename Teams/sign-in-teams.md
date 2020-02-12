---
title: Anmelden bei Microsoft Teams mit moderner Authentifizierung
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: So melden Sie sich bei Microsoft Teams mit moderner Authentifizierung an.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bb74338a3e46bb4e3a65fcbf2a69d56558dad61
ms.sourcegitcommit: f859843003b34feab18a3d2df34fdbb9858e7148
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41889438"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Anmelden bei Microsoft Teams mit moderner Authentifizierung
==========================

Microsoft Teams verwendet moderne Authentifizierung, um die Anmeldung einfach und sicher zu gestalten. Um zu erfahren, wie sich Benutzer bei Teams anmelden, lesen Sie bitte [Anmelden in Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>So funktioniert moderne Authentifizierung

Bei der modernen Authentifizierung handelt es sich um einen Prozess, der Teams mitteilt, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche E-Mail-Adresse und das Kennwort) bereits anderswo eingegeben haben, und dass Sie diese nicht erneut eingeben müssen, um die App zu starten. Das Erlebnis hängt von einigen Faktoren ab, beispielsweise wenn Benutzer mit Windows oder auf einem Mac arbeiten. Es hängt auch davon ab, ob Ihre Organisation die einstufige Authentifizierung oder die mehrstufige Authentifizierung aktiviert hat (die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Eingabe eines eindeutigen Codes, die Eingabe eines PIN-Codes oder die Verwendung eines Fingerabdrucks). Hier ist eine Übersicht über jedes Szenario moderner Authentifizierung.

### <a name="windows-users"></a>Windows-Benutzer 

- Wenn Benutzer sich bereits über ihr Office 365 Enterprise-Konto bei anderen Office-Anwendungen angemeldet haben, werden sie beim Start von Teams direkt zur App weitergeleitet. Sie müssen ihre Anmeldeinformationen nicht eingeben.

- Wenn Benutzer nicht woanders in ihrem Office 365 Enterprise-Konto angemeldet sind, werden sie beim Start von Teams gebeten, entweder eine ein- oder mehrstufige Authentifizierung (SFA oder MFA) anzugeben, je nachdem was Ihre Organisation für den Prozess festgelegt hat.

- Wenn Benutzer bei einem domänengebundenen Computer angemeldet sind, werden sie beim Start von Teams möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt durchzuführen, je nachdem, ob sich Ihre Organisation für MFA entschieden hat oder ob ihr Computer bereits MFA zum Anmelden erfordert. Wenn ihr Computer bereits MFA zur Anmeldung erfordert, startet die App automatisch, wenn  sie Teams öffnen.

- Wenn Benutzer bei einem in eine Domäne eingebundenen Computer angemeldet sind und Sie nicht möchten, dass ihre Benutzernamen im Anmeldebildschirm von Microsoft Teams vorab ausgefüllt werden, können Administratoren die folgende Windows-Registrierung so einrichten, dass das Vorab-Ausfüllen des Benutzernamens (UPN) deaktiviert ist:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Das Überspringen beim Vorab-Ausfüllen von Benutzernamen ist für Benutzernamen, die in ".local" oder ".corp" enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren. 


### <a name="mac-users"></a>Mac-Benutzer 

Wenn Benutzer Teams starten, kann ihr Computer ihre Anmeldeinformationen nicht von ihrem Office 365 Enterprise-Konto oder einer ihrer anderen Office-Anwendungen abrufen. Stattdessen wird eine Aufforderung zur Eingabe von SFA oder MFA angezeigt (abhängig von den Einstellungen Ihrer Organisation). Sobald die Benutzer ihre Anmeldeinformationen eingegeben haben, werden sie nicht mehr aufgefordert, sie erneut anzugeben. Von diesem Zeitpunkt an startet Teams automatisch, wenn sie am gleichen Computer arbeiten.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Kontowechsel nach Abschluss der modernen Authentifizierung

Wenn Benutzer an einem domänengebundenen Computer arbeiten (z.B. wenn ihr Mandant Kerberos aktiviert hat), können sie nach Abschluss der modernen Authentifizierung nicht mehr zwischen Benutzerkonten wechseln. Wenn Benutzer nicht an einem domänengebundenen Computer arbeiten, können sie zwischen Konten wechseln.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Abmeldung von Microsoft Teams nach Abschluss der modernen Authentifizierung
Um sich von Teams abzumelden, können Benutzer auf ihr Profilbild oben in der App klicken und dann **Abmelden** wählen. Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste klicken und dann **Abmelden** wählen. Sobald sie sich von Teams abgemeldet haben, müssen sie ihre Anmeldeinformationen erneut eingeben, um die App zu starten.

## <a name="urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche
Microsoft Teams setzt eine Internetverbindung voraus. Informationen zu Endpunkten, die für Kunden mit Microsoft Teams in Office 365-Plänen, Behörden und andere Clouds erreichbar sein sollten, finden Sie unter [URLs und IP-Adressbereiche für Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). 

> [!IMPORTANT]
> Microsoft Teams benötigt derzeit Zugriff (TCP-Port 443) auf den Google ssl.gstatic.com-Dienst (https://ssl.gstatic.com) für alle Benutzer. Dies gilt selbst dann, wenn Sie Gstatic nicht verwenden. Diese Anforderung wird demnächst (erste Hälfte 2020) aus Microsoft Teams entfernt. Dieser Artikel wird dann entsprechend aktualisiert.

## <a name="troubleshooting-modern-authentication"></a>Problembehandlung bei der modernen Authentifizierung

Moderne Authentifizierung ist für alle Organisationen verfügbar, die Teams verwenden. Wenn Benutzer also nicht in der Lage sind, den Prozess abzuschließen, liegt möglicherweise ein Problem mit Ihrer Domäne oder dem Office 365 Enterprise-Konto Ihrer Organisation vor. 

Weitere Informationen finden Sie unter [Wieso habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

