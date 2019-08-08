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
description: So können Sie sich mithilfe der modernen Authentifizierung bei Microsoft Teams anmelden.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af7ecffc6dbed108fdc3ec68802aac39aa4f54c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242511"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Anmelden bei Microsoft Teams mit moderner Authentifizierung
==========================

Microsoft Teams verwendet die moderne Authentifizierung, um die Anmelde Erfahrung einfach und sicher zu halten. Wenn Sie sehen möchten, wie sich Benutzer bei Teams anmelden, lesen Sie [Anmelden bei Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Funktionsweise der modernen Authentifizierung

Die moderne Authentifizierung ist ein Prozess, bei dem Teams wissen, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche e-Mail-Adresse und Ihr Kennwort) bereits an einem anderen Ort eingegeben haben, und Sie sollten nicht verpflichtet werden, Sie erneut einzugeben, um die APP zu starten. Die Erfahrung hängt von einigen Faktoren ab, wie etwa, wenn Benutzer in Windows oder auf einem Mac arbeiten. Es hängt auch davon ab, ob Ihre Organisation die einstufige Authentifizierung oder die mehrstufige Authentifizierung aktiviert hat (die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Bereitstellungeines eindeutigen Codes, das Eingeben einer PIN oder präsentieren eines Fingerabdrucks) Hier finden Sie einen Überblick über die einzelnen modernen Authentifizierungsszenarien.

### <a name="windows-users"></a>Windows-Benutzer: 

- Wenn sich Benutzer bereits über Ihr Office 365 Enterprise-Konto bei anderen Office-Apps angemeldet haben, werden Sie beim Starten von Teams direkt zur APP weitergeleitet. Sie müssen Ihre Anmeldeinformationen nicht eingeben.

- Wenn Benutzer nicht bei Ihrem Office 365 Enterprise-Konto angemeldet sind, wenn Sie Ihre Teams starten, werden Sie aufgefordert, eine Einzelfaktor-oder mehrstufige Authentifizierung (SFA oder MFA) bereitzustellen, je nachdem, was Ihre Organisation entschieden hat, wie Sie die zu bestehender Prozess.

- Wenn Benutzer bei einem mit der Domäne verbundenen Computer angemeldet sind, werden Sie möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt zu durchlaufen, je nachdem, ob Ihre Organisation MFA erfordert oder wenn Ihr Computer bereits MFA zur Anmeldung benötigt. Wenn Ihr Computer bereits MFA zur Anmeldung benötigt, wird die APP automatisch gestartet, wenn Sie Teams öffnen.

### <a name="mac-users"></a>Mac-Benutzer 

Wenn Benutzer Teams starten, kann Ihr Computer Ihre Anmeldeinformationen nicht von Ihrem Office 365 Enterprise-Konto oder einer anderen Office-Anwendung abrufen. Stattdessen sehen Sie eine Aufforderung, in der Sie nach SFA oder MFA gefragt werden (je nach den Einstellungen Ihrer Organisation). Nachdem die Benutzer ihre Anmeldeinformationen eingegeben haben, müssen Sie Sie nicht erneut angeben. Ab diesem Zeitpunkt werden die Teams automatisch gestartet, wenn Sie am gleichen Computer arbeiten.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Wechseln von Konten nach Abschluss der modernen Authentifizierung

Wenn Benutzer an einem Computer mit einer Domäne arbeiten (Wenn beispielsweise der Mandant Kerberos aktiviert hat), können Benutzerkonten nicht gewechselt werden, nachdem Sie die moderne Authentifizierung abgeschlossen haben. Wenn Benutzer nicht an einem Computer mit Domänenbeitritt arbeiten, können Sie die Konten wechseln.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Abmelden bei Microsoft Teams nach Abschluss der modernen Authentifizierung
Zum Abmelden von Teams können Benutzer oben in der APP auf Ihr Profilbild klicken und dann Abmelden auswählen. **** Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste **** klicken und dann Abmelden auswählen. Nachdem Sie sich bei Microsoft Teams abgemeldet haben, müssen Sie Ihre Anmeldeinformationen erneut eingeben, um die APP zu starten.

## <a name="troubleshooting-modern-authentication"></a>Problembehandlung bei der modernen Authentifizierung

Die moderne Authentifizierung ist für alle Organisationen verfügbar, in denen Teams verwendet werden, wenn Benutzer den Vorgang also nicht abschließen können, liegt möglicherweise ein Fehler mit Ihrer Domäne oder dem Office 365 Enterprise-Konto Ihrer Organisation vor. 

Weitere Informationen finden Sie unter [Warum habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

