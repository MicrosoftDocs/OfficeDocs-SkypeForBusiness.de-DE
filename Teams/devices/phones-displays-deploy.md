---
title: Bereitstellen von Teams-Telefonen und -Anzeigen mit Intune
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
description: Dieser Artikel bietet eine Übersicht über die von Microsoft Teams unterstützten Features.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120777"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Bereitstellen von Teams-Telefonen und -Anzeigen mit Intune

In diesem Artikel erhalten Sie eine Übersicht über die Bereitstellung von Teams-Telefonen und Teams-Displays mit Intune.

## <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist ein Azure Active Directory (Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Telefone und Teams-Displays), die auf Teams zugreifen, bei Intune registriert werden, und ihre Einstellungen müssen Ihren Richtlinien entsprechen.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert bedingter Zugriff, dass sich ein Benutzer bei der Teams-App auf dem Gerät anmelden oder diese verwenden kann.

In der Regel werden in Intune definierte Compliancerichtlinien Benutzergruppen zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für ihr Android-Smartphone und für jedes Android-basierte Teams-Gerät, bei dem user@contoso.com ist.

Wenn Sie bedingten Zugriff verwenden, bei dem die Intune-Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation einige Dinge einrichten, die Sie einrichten müssen, um eine erfolgreiche Intune-Registrierung zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Gerät "Teams" registriert, muss für Intune lizenziert sein.  Solange das Microsoft Teams-Gerät bei einem Benutzerkonto mit einer gültigen Intune-Lizenz angemeldet ist, wird das Gerät automatisch im Rahmen des Anmeldevorgangs bei Microsoft Intune registriert.
- **Konfigurieren von Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune-Mandanten für die Registrierung von Android-Geräteadministratoren eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von Intune zum Registrieren von Teams Android-basierten Geräten

Android-basierte Geräte von Teams werden in Intune über die Verwaltung von Android-Geräten verwaltet. Bevor Geräte bei Intune registriert werden können, müssen Sie einige grundlegende Schritte ausführen.  Wenn Sie Geräte bereits mit Intune verwalten, haben Sie wahrscheinlich alle diese Dinge bereits erledigt.  Andern falls nicht, gehen Sie wie hier vor:

1. Legen Sie intune MDM (Mobile Device Management) Authority (Verwaltung mobiler Geräte) ein.  Wenn Sie Intune noch nie verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Festlegen der Verwaltungsbehörde für mobile Geräte.](/intune/fundamentals/mdm-authority-set)  Dies ist ein einmaler Schritt, der beim Erstellen eines neuen Intune-Mandanten durchgeführt werden muss.
2. Aktivieren Sie die Registrierung für Android-Geräteadministratoren. Android-basierte Teams-Geräte werden mit Intune als Geräteadministratorgeräte verwaltet.  Die Geräteadministratorregistrierung ist für neu erstellte Mandanten standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Registrierung für Android-Geräteadministratoren.](/intune/enrollment/android-enroll-device-administrator)
3. Weisen Sie Benutzern Lizenzen zu. Benutzern von Teams-Geräten, die sich bei Intune registrieren, muss eine gültige Intune-Lizenz zugewiesen werden. Weitere Informationen finden Sie unter Zuweisen von Lizenzen [zu Benutzern, damit sie Geräte in Intune registrieren können.](/intune/fundamentals/licenses-assign)
4. Zuweisen von Compliancerichtlinien für Geräteadministratoren.  Erstellen Sie eine Compliancerichtlinie für Android-Geräteadministratoren, und weisen Sie sie der Azure Active Directory-Gruppe zu, die die Benutzer enthält, die sich bei den Teams-Geräten anmelden. Weitere Informationen finden Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für [Geräte, die Sie mit Intune verwalten.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Mehr dazu

[Telefone für Teams](phones-for-teams.md)

[FÜR Microsoft Teams zertifizierte IP Phones](teams-ip-phones.md)

[Anzeigen von Teams](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)