---
title: Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: In diesem Thema wird beschrieben, wie Benutzer mit lokalen PSTN-Anbindung für Telefonsystem in Office 365 zu aktivieren. Vor dem Durchführen der Schritte in diesem Thema sollten Sie Folgendes lesen:.
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234070"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server
 
In diesem Thema wird beschrieben, wie Benutzer mit lokalen PSTN-Anbindung für Telefonsystem in Office 365 zu aktivieren. Vor dem Durchführen der Schritte in diesem Thema sollten Sie Folgendes lesen:.
  
- Weitere Informationen zum Einrichten von hybridkonnektivität finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online planen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Informationen zur Planung der Bereitstellung finden Sie [Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server planen](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Weitere Informationen zum Telefonsystem in Office 365, einschließlich der Lizenzierung und Pläne, finden Sie unter [PSTN aufrufen Abonnements Skype für Unternehmen](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Migrieren von Benutzern zu Telefonsystem in Office 365 mit lokalen PSTN-Anbindung

Bevor Sie Ihre Benutzer in Skype für Business Online verschieben, wird empfohlen, dass Sie Ihre Benutzer lokal in Skype für Business Server oder Lync Server 2013 aktivieren, und verschieben Sie sie online. Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und im Abschnitt besondere Aspekte [aktivieren die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) ausgeführt wird (während der Benutzer verwaltet werden lokal). 
  
Alle Benutzer müssen in Active Directory lokal erstellt und zu Office 365 mit der unterstützten Version des Azure AD-Connector synchronisiert werden. Benutzer kann nicht aktiviert werden, für Telefonsystem in Office 365, die direkt in Azure AD erstellt wurden. Wenn Sie möchten Telefonsystem in Office 365 mit lokalen PSTN-Anbindung für einen Benutzer zu aktivieren, die in Azure AD erstellt wurde, müssen Sie zum Erstellen eines neuen Kontos für diesen Benutzer in Ihrer lokalen AD, Konto lokale konfigurieren, und klicken Sie dann synchronisieren das Konto verwenden eine unterstützte Version des Azure AD Verbinder. 
  
Aktivieren eines Benutzers für Telefonsystem in Office 365 mit lokalen PSTN-Anbindung und anschließendes Verschieben auf Skype für Business Online müssen die folgenden Schritte aus:
  
- [Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (ausgeführt, während die Benutzer befinden sich lokal).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).
    
- [Synchronisieren von Benutzern, die Lizenzen Cloud und zuweisen](synchronize-users-to-the-cloud-and-assign-licenses.md) (erfolgt mithilfe von Office 365).
    
- [Verschieben Sie lokale Benutzer in Skype für Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (erfolgt mithilfe von Windows PowerShell: lokal, aber Ihre Office 365-Administrator-Anmeldeinformationen verwenden).
    
- [Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (mithilfe von Remote-PowerShell ausgeführt.
    

