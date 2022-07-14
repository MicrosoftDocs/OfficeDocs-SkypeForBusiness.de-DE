---
title: Bereitstellen von Teams-Telefonen, Teams-Displays, Teams-Bereichen und Microsoft Teams-Räume unter Android mithilfe von Intune
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Dieser Artikel enthält eine Übersicht über und Features, die von Microsoft Teams Android-Geräten unterstützt werden.
ms.openlocfilehash: 5522c29c74eb9679d26d13627dcb69b315dc33fd
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790310"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Bereitstellen von Teams-Telefonen, Teams-Displays, Teams-Bereichen und Microsoft Teams-Räume unter Android mithilfe von Intune

In diesem Artikel erhalten Sie eine Übersicht über die Bereitstellung von Teams-Telefonen, Teams-Displays, Teams-Bereichen und Microsoft Teams-Räume unter Android mithilfe von Intune.

## <a name="conditional-access"></a>Bedingter Zugriff

Der bedingte Zugriff ist ein Azure Active Directory (Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, die auf Ihre Office 365 Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Telefonen, Teams-Displays, Teams-Bereichen und Microsoft Teams-Räume unter Android), die auf Teams zugreifen, in Intune registriert werden, und ihre Einstellungen müssen Ihren Richtlinien entsprechen.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, aber seine Einstellungen nicht Ihren Richtlinien entsprechen, verhindert der bedingte Zugriff, dass sich ein Benutzer bei der Teams-App auf dem Gerät anmeldet oder verwendet.

In der Regel werden in Intune definierte Compliancerichtlinien Gruppen von Benutzern zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für ihr Android-Smartphone und alle Android-basierten Teams-Geräte, bei denen sich user@contoso.com anmelden.

Wenn Sie den bedingten Zugriff verwenden, für den Intune Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation einige Dinge einrichten, um eine erfolgreiche Intune Registrierung zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Teams-Gerät anmeldet, muss für Intune lizenziert sein.  Solange das Teams-Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige Intune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldevorgangs automatisch in Microsoft Intune registriert.
- **Konfigurieren sie Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune Mandanten für die Registrierung des Android-Geräteadministrators eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren Intune zum Registrieren von Android-basierten Teams-Geräten

Android-basierte Teams-Geräte werden von Intune über die Verwaltung des Android-Geräteadministrators (DA) verwaltet. Bevor Geräte bei Intune registriert werden können, müssen sie einige grundlegende Schritte ausführen.  Wenn Sie bereits heute Geräte mit Intune verwalten, haben Sie wahrscheinlich bereits alle diese Dinge erledigt.  Wenn nicht, gehen Sie wie folgt vor:

> [!NOTE]
> - Wenn Mandantenadministratoren möchten, dass Telefone für gemeinsame Bereiche bei Intune registriert werden, müssen sie dem Konto eine Intune Lizenz hinzufügen und die Schritte für Intune Registrierung ausführen.
> - Wenn das Benutzerkonto, das für die Anmeldung bei einem Teams-Gerät verwendet wird, nicht für Intune lizenziert ist, müssen Intune Compliancerichtlinien und Registrierungseinschränkungen für das Konto deaktiviert werden.



1. Legen Sie Intune MDM-Autorität (Verwaltung mobiler Geräte) fest.  

   Wenn Sie Intune noch nie verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Festlegen der Verwaltungsbehörde für mobile Geräte](/intune/fundamentals/mdm-authority-set).  Dies ist ein einmaliger Schritt, der beim Erstellen eines neuen Intune Mandanten ausgeführt werden muss.
1. Aktivieren Sie die Registrierung des Android-Geräteadministrators.
  
   Android-basierte Teams-Geräte werden als Geräteadministratorgeräte mit Intune verwaltet.  Die Geräteadministratorregistrierung ist für neu erstellte Mandanten standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Registrierung des Android-Geräteadministrators](/intune/enrollment/android-enroll-device-administrator).
1. Weisen Sie Benutzern Lizenzen zu. 
 
   Benutzern von Teams-Geräten, die sich für Intune registrieren, muss eine gültige Intune-Lizenz zugewiesen werden. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern, damit sie Geräte in Intune registrieren können](/intune/fundamentals/licenses-assign).
1. Weisen Sie Geräteadministrator-Compliancerichtlinien zu.  

   1. Erstellen Sie eine Android-Geräteadministrator-Compliancerichtlinie.

   1. Weisen Sie sie der Azure Active Directory-Gruppe zu, die die Benutzer enthält, die sich bei den Teams-Geräten anmelden werden. Weitere Informationen finden [Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für Geräte, die Sie mit Intune verwalten](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Siehe auch

[Telefone für Teams](phones-for-teams.md)

[FÜR Microsoft Teams zertifizierte IP-Telefone](teams-ip-phones.md)

[Teams-Anzeige](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)
