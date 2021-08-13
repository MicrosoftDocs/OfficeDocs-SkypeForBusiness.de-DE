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
ms.openlocfilehash: 1ccf933cfb0f4e9eab4af4f884cbd6503d0667138d56d8c005574c57d839626a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321477"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Bereitstellen Teams von Telefonen und Teams mit Intune

Dieser Artikel enthält eine Übersicht über die Bereitstellung. Teams von Mobiltelefonen und Teams mit Intune anzeigen.

## <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist ein Azure Active Directory (Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, auf die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Telefonen und Teams-Anzeigen), die auf Teams zugreifen, bei Intune registriert sein, und deren Einstellungen müssen Ihre Richtlinien einhalten.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert bedingter Zugriff, dass sich ein Benutzer bei der Teams-App auf dem Gerät anmelden oder diese verwenden kann.

In der Regel werden in Intune definierte Compliancerichtlinien Benutzergruppen zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für ihr Android-Smartphone und jedes Android-basierte Teams-Gerät, bei dem user@contoso.com ist.

Wenn Sie den bedingten Zugriff verwenden, für den die Intune-Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation ein paar Dinge einrichten, um eine erfolgreiche Intune-Registrierung zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Teams angemeldet hat, muss für Intune lizenziert sein.  Solange das Teams-Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige Intune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldevorgangs automatisch in Microsoft Intune registriert.
- **Konfigurieren von Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune-Mandanten für die Registrierung durch den Android-Geräteadministrator eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von Intune zum Registrieren Teams Android-basierten Geräten

Teams Android-basierte Geräte werden von Intune über die Verwaltung durch den Android-Geräteadministrator (Da) verwaltet. Bevor Geräte bei Intune registriert werden können, müssen Sie ein paar grundlegende Schritte ausführen.  Wenn Sie Geräte bereits heute mit Intune verwalten, haben Sie wahrscheinlich bereits all diese Dinge erledigt.  Wenn nicht, gehen Sie wie hier gezeigt vor:

> [!NOTE]
> - Wenn Mandantenadministratoren allgemeine Telefone in Intune registrieren möchten, müssen sie dem Konto eine Intune-Lizenz hinzufügen und die Schritte für die Intune-Registrierung ausführen.
> - Wenn das Benutzerkonto, das zum Anmelden bei einem Teams-Gerät verwendet wurde, nicht für Intune lizenziert ist, müssen Intune-Compliancerichtlinien und Registrierungseinschränkungen für das Konto deaktiviert werden.



1. Legen Sie Intune MDM -Autorität (Verwaltung mobiler Geräte) festgelegt.  

   Wenn Sie Intune noch nie zuvor verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Festlegen der Verwaltungsbehörde für mobile Geräte.](/intune/fundamentals/mdm-authority-set)  Dies ist ein einmal zu erledigener Schritt beim Erstellen eines neuen Intune-Mandanten.
1. Aktivieren Sie die Registrierung des Android-Geräteadministrators.
  
   Android-basierte Teams Geräte werden mit Intune als Geräteadministratorgeräte verwaltet.  Die Geräteadministratorregistrierung ist für neu erstellte Mandanten standardmäßig deaktiviert. Weitere Informationen [finden Sie unter Registrierung des Android-Geräteadministrators.](/intune/enrollment/android-enroll-device-administrator)
1. Zuweisen von Lizenzen zu Benutzern 
 
   Benutzern von Teams, die sich bei Intune registrieren, muss eine gültige Intune-Lizenz zugewiesen sein. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern, damit diese Geräte in Intune registrieren können.](/intune/fundamentals/licenses-assign)
1. Zuweisen von Compliancerichtlinien für Geräteadministratoren  

   a. Erstellen Sie eine Compliancerichtlinie für den Android-Geräteadministrator.

   b. Weisen Sie sie der Azure Active Directory-Gruppe zu, die die Benutzer enthält, die sich bei den Teams anmelden. Weitere Informationen finden Sie unter Verwenden von [Compliancerichtlinien zum Festlegen von Regeln für Geräte, die Sie mit Intune verwalten.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Mehr dazu

[Telefone für Teams](phones-for-teams.md)

[Ip Phones certified for Microsoft Teams](teams-ip-phones.md)

[Teams anzeigen](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)