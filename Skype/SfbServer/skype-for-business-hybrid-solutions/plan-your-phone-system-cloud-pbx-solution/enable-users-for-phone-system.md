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
description: In diesem Thema wird beschrieben, wie Sie Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren. Bevor Sie die Schritte in diesem Thema durchführen, sollten Sie folgendes lesen:.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359141"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Ermöglichen, dass Benutzer des Telefonsystems eine lokale Festnetzanbindung in Skype for Business Server herstellen

In diesem Thema wird beschrieben, wie Sie Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren. Bevor Sie die Schritte in diesem Thema durchführen, sollten Sie folgendes lesen:.
  
- Informationen zum Einrichten von Hybrid Konnektivität finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Informationen zum Planen der Bereitstellung finden Sie unter [Plan Phone System with on-premises PSTN Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Weitere Informationen zum Telefon System einschließlich Lizenzierung und Plänen finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Verschieben von Benutzern in ein Telefon System mit lokaler PSTN-Konnektivität

Bevor Sie Ihre Benutzer in Skype for Business Online verschieben, wird empfohlen, dass Sie Ihre Benutzer lokal in Skype for Business Server oder lync Server 2013 aktivieren und dann Online verschieben. Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und im Abschnitt "spezielle Überlegungen" unter [Aktivieren der Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal verwaltet werden). 
  
Alle Benutzer müssen in Active Directory lokal erstellt und mit der unterstützten Version von Azure AD Connector mit Microsoft 365 oder Office 365 synchronisiert werden. Sie können Benutzer für das Telefon System nicht in Office 365 aktivieren, die direkt in Azure AD erstellt wurden. Wenn Sie das Telefon System mit lokaler PSTN-Konnektivität für einen Benutzer aktivieren möchten, der in Azure AD erstellt wurde, müssen Sie ein neues Konto für diesen Benutzer in Ihrer lokalen AD erstellen, das Konto lokal konfigurieren und dann das Konto mithilfe einer unterstützten Version des Azure AD Connector-Tools synchronisieren. 
  
Wenn Sie einen Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren und anschließend in Skype for Business Online verschieben möchten, müssen Sie die folgenden Schritte ausführen:
  
- [Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal verwaltet werden).
    
- [Zuweisen einer VoIP-Routing Richtlinie](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).
    
- [Synchronisieren von Benutzern mit der Cloud und Zuweisen von Lizenzen](synchronize-users-to-the-cloud-and-assign-licenses.md) (erfolgt mithilfe von Office 365).
    
- [Lokale Benutzer werden in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (mit Windows PowerShell lokal, jedoch mit den Anmeldeinformationen des Office 365 Administrators) verlagert.
    
- [Aktivieren von Benutzern für Enterprise-VoIP-Online-und Telefon System-Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (wird mithilfe von Remote-PowerShell ausgeführt.
    

