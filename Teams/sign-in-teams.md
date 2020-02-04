---
title: Anmelden bei Microsoft Teams mit moderner Authentifizierung
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: So melden Sie sich bei Microsoft Teams mit moderner Authentifizierung an.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d266799bf2bc2cab9cd107836f9017bd7dc369bf
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41678969"
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

- Wenn Benutzer bei einem von der Domäne verbundenen Computer angemeldet sind und nicht möchten, dass der Benutzername auf dem Anmeldebildschirm der Teams vorinstalliert ist, können Administratoren die folgende Windows-Registrierung so einrichten, dass die vorauffüllung des Benutzernamens deaktiviert wird: Computer \ HKEY_CURRENT_USER \software\ Microsoft\Office\Teams DisableUpnSuffixCheck (REG_DWORD) 0x00000001 (1)

  Hinweis: das Überspringen von Benutzernamen-Pre-Fill für Benutzernamen, die in ". local" oder ". Corp" enden, ist standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren. 


### <a name="mac-users"></a>Mac-Benutzer 

Wenn Benutzer Teams starten, kann ihr Computer ihre Anmeldeinformationen nicht von ihrem Office 365 Enterprise-Konto oder einer ihrer anderen Office-Anwendungen abrufen. Stattdessen wird eine Aufforderung zur Eingabe von SFA oder MFA angezeigt (abhängig von den Einstellungen Ihrer Organisation). Sobald die Benutzer ihre Anmeldeinformationen eingegeben haben, werden sie nicht mehr aufgefordert, sie erneut anzugeben. Von diesem Zeitpunkt an startet Teams automatisch, wenn sie am gleichen Computer arbeiten.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Kontowechsel nach Abschluss der modernen Authentifizierung

Wenn Benutzer an einem domänengebundenen Computer arbeiten (z.B. wenn ihr Mandant Kerberos aktiviert hat), können sie nach Abschluss der modernen Authentifizierung nicht mehr zwischen Benutzerkonten wechseln. Wenn Benutzer nicht an einem domänengebundenen Computer arbeiten, können sie zwischen Konten wechseln.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Abmeldung von Microsoft Teams nach Abschluss der modernen Authentifizierung
Um sich von Teams abzumelden, können Benutzer auf ihr Profilbild oben in der App klicken und dann **Abmelden** wählen. Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste klicken und dann **Abmelden** wählen. Sobald sie sich von Teams abgemeldet haben, müssen sie ihre Anmeldeinformationen erneut eingeben, um die App zu starten.

## <a name="troubleshooting-modern-authentication"></a>Problembehandlung bei der modernen Authentifizierung

Moderne Authentifizierung ist für alle Organisationen verfügbar, die Teams verwenden. Wenn Benutzer also nicht in der Lage sind, den Prozess abzuschließen, liegt möglicherweise ein Problem mit Ihrer Domäne oder dem Office 365 Enterprise-Konto Ihrer Organisation vor. 

Weitere Informationen finden Sie unter [Wieso habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

