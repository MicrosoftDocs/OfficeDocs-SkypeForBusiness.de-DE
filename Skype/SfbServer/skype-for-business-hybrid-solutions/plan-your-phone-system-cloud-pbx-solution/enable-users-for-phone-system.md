---
title: Aktivieren von Benutzern für das Telefon System in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'In diesem Thema wird beschrieben, wie Benutzer für Telefonsysteme in Office 365 mit lokalen PSTN-Konnektivität aktiviert werden. Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie folgendes lesen:'
ms.openlocfilehash: c0c9f840c15e40aa3a78b69a5cbbf2f721251bbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802185"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Aktivieren von Benutzern für das Telefon System in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server
 
In diesem Thema wird beschrieben, wie Benutzer für Telefonsysteme in Office 365 mit lokalen PSTN-Konnektivität aktiviert werden. Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie folgendes lesen:
  
- Informationen zum Einrichten von Hybrid Konnektivität finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Informationen zum Planen der Bereitstellung finden Sie unter [Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Weitere Informationen zu Telefonsystemen in Office 365, einschließlich Lizenzierung und Pläne, finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Verschieben von Benutzern in das Telefon System in Office 365 mit lokalen PSTN-Konnektivität

Bevor Sie Ihre Benutzer in Skype for Business Online verschieben, empfiehlt es sich, die Benutzer lokal in Skype for Business Server oder lync Server 2013 zu aktivieren und dann online zu verschieben. Weitere Informationen finden Sie unter [Planen einer hybriden Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und dem Abschnitt besondere Überlegungen unter [Aktivieren der Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal verwaltet werden). 
  
Alle Benutzer müssen mit der unterstützten Version von Azure AD Connector in Active Directory lokal erstellt und mit Office 365 synchronisiert werden. Sie können Benutzer für Telefonsysteme in Office 365, die direkt in Azure AD erstellt wurden, nicht aktivieren. Wenn Sie das Telefon System in Office 365 mit lokalen PSTN-Konnektivität für einen Benutzer aktivieren möchten, der in Azure AD erstellt wurde, müssen Sie ein neues Konto für diesen Benutzer in Ihrer lokalen Anzeige erstellen, das Konto lokal konfigurieren und dann das Konto mithilfe von eine unterstützte Version des Azure AD Connector-Tools. 
  
Wenn Sie einen Benutzer für das Telefon System in Office 365 mit lokalen PSTN-Konnektivität aktivieren und dann in Skype for Business Online verschieben, müssen Sie die folgenden Schritte ausführen:
  
- [Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal gehostet werden).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).
    
- [Synchronisieren Sie Benutzer mit der Cloud, und weisen Sie Lizenzen zu](synchronize-users-to-the-cloud-and-assign-licenses.md) (ausgeführt mit Office 365).
    
- [Verschieben Sie lokale Benutzer in Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (mit Windows PowerShell lokal, aber mit den Office 365-Administratoranmeldeinformationen).
    
- [Aktivieren von Benutzern für Enterprise Voice Online und Telefon System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (wird mithilfe von Remote-PowerShell ausgeführt.
    

