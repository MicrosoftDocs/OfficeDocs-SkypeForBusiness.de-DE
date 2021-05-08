---
title: Bereitstellen Teams von Telefonen und Teams mit Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Dieser Artikel bietet eine Übersicht über die von der Microsoft Teams unterstützten Features.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120777"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Bereitstellen Teams von Telefonen und Teams mit Intune

Dieser Artikel gibt Ihnen einen Überblick über das Bereitstellen von Teams und anzeigen Teams mithilfe von Intune.

## <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist ein Azure Active Directory (Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, auf die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Telefonen und Teams-Anzeigen), die auf Teams zugreifen, bei Intune registriert sein, und deren Einstellungen müssen Ihre Richtlinien einhalten.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert bedingter Zugriff, dass sich ein Benutzer bei der Teams-App auf dem Gerät anmelden oder diese verwenden kann.

In der Regel werden in Intune definierte Compliancerichtlinien Benutzergruppen zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für ihr Android-Smartphone und jedes Android-basierte Teams-Gerät, bei dem user@contoso.com ist.

Wenn Sie den bedingten Zugriff verwenden, für den die Intune-Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation ein paar Dinge einrichten, um eine erfolgreiche Intune-Registrierung zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Teams angemeldet hat, muss für Intune lizenziert sein.  Solange das Teams-Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige Intune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldevorgangs automatisch Microsoft Intune registriert.
- **Konfigurieren von Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune-Mandanten für die Registrierung durch den Android-Geräteadministrator eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von Intune zum Registrieren Teams Android-basierten Geräten

Teams Android-basierte Geräte werden in Intune über die Verwaltung durch den Android-Geräteadministrator (Da) verwaltet. Bevor Geräte bei Intune registriert werden können, müssen Sie ein paar grundlegende Schritte ausführen.  Wenn Sie Geräte bereits heute mit Intune verwalten, haben Sie wahrscheinlich bereits all diese Dinge erledigt.  Wenn nicht, gehen Sie wie hier gezeigt vor:

1. Legen Sie Intune MDM -Autorität (Verwaltung mobiler Geräte) festgelegt.  Wenn Sie Intune noch nie verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Festlegen der Verwaltungsbehörde für mobile Geräte.](/intune/fundamentals/mdm-authority-set)  Dies ist ein einmal zu erledigener Schritt beim Erstellen eines neuen Intune-Mandanten.
2. Aktivieren Sie die Registrierung des Android-Geräteadministrators. Android-basierte Teams werden als Geräteadministratorgeräte mit Intune verwaltet.  Die Geräteadministratorregistrierung ist für neu erstellte Mandanten standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Registrierung für Android-Geräteadministratoren.](/intune/enrollment/android-enroll-device-administrator)
3. Zuweisen von Lizenzen zu Benutzern Benutzern von Teams, die sich bei Intune registrieren, muss eine gültige Intune-Lizenz zugewiesen sein. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern, damit diese Geräte in Intune registrieren können.](/intune/fundamentals/licenses-assign)
4. Zuweisen von Compliancerichtlinien für Geräteadministratoren  Erstellen Sie eine Android-Geräteadministrator-Compliancerichtlinie, und weisen Sie sie der Gruppe "Azure Active Directory" zu, die die Benutzer enthält, die sich bei den Teams anmelden. Weitere Informationen finden Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für [Geräte, die Sie mit Intune verwalten.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Mehr dazu

[Telefone für Teams](phones-for-teams.md)

[Ip Phones certified for Microsoft Teams](teams-ip-phones.md)

[Teams anzeigen](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)