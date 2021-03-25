---
title: Ermöglichen, dass Benutzer des Telefonsystems eine lokale Festnetzanbindung in Skype for Business Server herstellen
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
description: 'In diesem Thema wird beschrieben, wie Benutzer für Das Telefonsystem mit einer lokalen PSTN-Verbindung aktiviert werden. Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie Folgendes lesen: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120867"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Ermöglichen, dass Benutzer des Telefonsystems eine lokale Festnetzanbindung in Skype for Business Server herstellen

In diesem Thema wird beschrieben, wie Benutzer für Das Telefonsystem mit einer lokalen PSTN-Verbindung aktiviert werden. Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie Folgendes lesen: .
  
- Informationen zum Einrichten von Hybridkonnektivität finden Sie unter Planen der Hybridkonnektivität zwischen [Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und Skype for Business Online und Bereitstellen der Hybridkonnektivität zwischen Skype for Business Server und Skype for Business [Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Weitere Informationen zur Planung Ihrer Bereitstellung finden Sie unter [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Weitere Informationen zum Telefonsystem, einschließlich Lizenzierung und Plänen, finden Sie unter [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Verschieben von Benutzern zu Telefonsystem mit lokalen PSTN-Verbindungen

Bevor Sie Ihre Benutzer zu Skype for Business Online verschieben, wird empfohlen, dass Sie Ihre Benutzer lokal in Skype for Business Server oder Lync Server 2013 aktivieren und dann online verschieben. Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und the special considerations section of Enable the users for Enterprise-VoIP on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises). 
  
Alle Benutzer müssen lokal in Active Directory erstellt und mithilfe der unterstützten Version von Azure AD Connector mit Microsoft 365 oder Office 365 synchronisiert werden. Benutzer für Telefonsystem in Office 365, die direkt in Azure AD erstellt wurden, können nicht aktiviert werden. Wenn Sie das Telefonsystem mit einer lokalen PSTN-Verbindung für einen Benutzer aktivieren möchten, der in Azure AD erstellt wurde, müssen Sie ein neues Konto für diesen Benutzer in Ihrem lokalen AD erstellen, das Konto lokal konfigurieren und dann das Konto mithilfe einer unterstützten Version des Azure AD Connector-Tools synchronisieren. 
  
Das Aktivieren eines Benutzers für das Telefonsystem mit einer lokalen PSTN-Verbindung und das anschließende Verschieben zu Skype for Business Online erfordert die folgenden Schritte:
  
- [Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (ausgeführt, während die Benutzer lokal zu Hause sind).
    
- [Weisen Sie eine Voiceroutingrichtlinie zu](assign-a-voice-routing-policy.md) (ausgeführt, während die Benutzer lokal heimgeheimt werden).
    
- [Synchronisieren Sie Benutzer mit der Cloud, und weisen Sie Lizenzen](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) zu (ausgeführt mit Office 365).
    
- [Verschieben Sie lokale Benutzer zu Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (ausgeführt mit Windows PowerShell lokalen, aber mit Ihren Office 365-Administratoranmeldeinformationen).
    
- [Aktivieren Sie Benutzer für Enterprise-VoIP und Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) des Telefonsystems (mithilfe von Remote PowerShell.
