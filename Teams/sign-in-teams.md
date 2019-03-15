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
description: Informationen zur Anmeldung bei Microsoft-Teams, mithilfe der modernen Authentifizierung.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc79f6913a2996734b34d589f124c440eb9835e
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641105"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Anmelden bei Microsoft Teams mit moderner Authentifizierung
==========================

Microsoft-Teams, wird die modernen Authentifizierung, um die Anmeldung einfach und sicher zu halten. Um herauszufinden, wie Benutzer Teams anmelden, lesen Sie [Teams anmelden](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Wie modernen Funktionsweise der Authentifizierung

Moderne Authentifizierung ist ein Prozess, der kann Teams wissen, dass Benutzer bereits ihre Anmeldeinformationen (wie ihre geschäftliche e-Mail und Kennwort) an anderer Stelle eingegeben haben und sollte nicht benötigt werden, geben sie erneut aus, um die Anwendung zu starten. Die Erfahrung variiert je nach einige Faktoren, wie wenn Benutzer unter Windows oder auf einem Mac arbeiten Es wird ebenfalls variieren abhängig davon, ob Ihre Organisation einfache oder mehrstufige Authentifizierung aktiviert hat (Multi-Factor Authentication sind meist Überprüfen der Anmeldeinformationen über ein Telefon, bietet einen eindeutigen Code, indem Sie eine PIN eingeben oder Präsentation eines Fingerabdrucks). Nachfolgend finden Sie einen Überblick über jedes Szenario modernen Authentifizierung.

### <a name="windows-users"></a>Windows-Benutzer: 

- Wenn Benutzer bereits für andere Office-apps über ihr Office 365 Enterprise-Konto beim Starten von Teams angemeldet haben sind die für die app gerade verwendet. Es ist nicht erforderlich sind, um ihre Anmeldeinformationen eingeben.

- Wenn der Benutzer nicht an anderer Stelle, ihre Office 365 Enterprise-Konto angemeldet sind beim Starten von Teams, sie aufgefordert werden, bieten einfache oder mehrstufige Authentifizierung (SFA oder mehrstufiger Authentifizierung das), je nachdem was Ihrem Unternehmen beschlossen wurde, muss auch die Prozess zum unterstützen könnte.

- Wenn Benutzer zu einer Domäne gehörenden Computer beim Starten von Teams angemeldet sind, sie werden möglicherweise aufgefordert, wechseln über eine weitere Authentifizierungsschritt, je nachdem, ob Ihre Organisation mehrstufiger Authentifizierung das erforderlich, um bestätigt oder ihren Computer bereits mehrstufiger Authentifizierung das zur Anmeldung bei erfordert. Wenn ihre Computer bereits mehrstufiger Authentifizierung das benötigt So melden Sie sich beginnt beim von Teams, die app automatisch öffnen.

### <a name="mac-users"></a>Mac-Benutzer 

Wenn Benutzer Teams starten, werden ihren Computer kann nicht ihre Anmeldeinformationen für ihre Office 365 Enterprise-Konto oder eine ihrer anderen Office-Anwendung abgerufen. Stattdessen wird gefragt, deren für SFA oder mehrstufiger Authentifizierung das (abhängig von Ihrer Organisation Einstellungen) angezeigt. Nachdem Benutzer ihre Anmeldeinformationen eingeben, werden sie wird nicht benötigt diese erneut bereitstellen. Ab diesem Zeitpunkt auf Teams, die automatisch startet immer auf demselben Computer arbeiten.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Wechseln nach Abschluss der modernen Authentifizierung Konten

Wenn Benutzer auf einer Domäne gehörenden Computer (beispielsweise, wenn ihre Mandanten Kerberos aktiviert hat) arbeiten, können nicht sie Benutzerkonten wechseln, sobald sie modernen Authentifizierung abgeschlossen haben. Wenn Benutzer nicht auf einer Domäne gehörenden Computer arbeiten, können sie Konten wechseln.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Abmelden von Microsoft-Teams, klicken Sie nach Abschluss der modernen Authentifizierung
Um sich abzumelden Teams können Benutzer klicken Sie auf das Profilbild am oberen Rand der app, und wählen Sie dann auf **Abmelden**. Sie können auch auf das app-Symbol in der Taskleiste und wählen Sie dann auf **Abmelden**. Sobald sie abmelden Teams haben, müssen sie ihre Anmeldeinformationen erneut aus, um die app starten eingeben.

## <a name="troubleshooting-modern-authentication"></a>Problembehandlung bei modernen Authentifizierung

Moderne Authentifizierung ist für jede Organisation, dass Verwendungsmöglichkeiten Teams, also wenn Benutzer nicht für die Durchführung des Aktivierungsvorgangs können möglicherweise Problem in Ihrer Domäne oder Office 365 Enterprise-Konto Ihrer Organisation verfügbar sind. 

Weitere Informationen finden Sie unter [Warum treten Probleme bei der Anmeldung an Microsoft-Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

