---
title: Konfigurieren von Konten für Microsoft-Teams Räume
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Lesen Sie dieses Thema Weitere Informationen zu Exchange Konfigurieren von Konten für Microsoft-Teams Chatrooms und Skype für Unternehmen.
ms.openlocfilehash: f276510e633e30d248d5c5d46277e04deaf043b0
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362816"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft-Teams Räume
 
Lesen Sie dieses Thema Informationen zur Microsoft-Teams Chatrooms und wie es mit Exchange und Skype für Unternehmen integriert ist.
  
In diesem Thema werden zum Erstellen von Konten, die von Microsoft-Teams Räumen in Microsoft Exchange und Skype für Unternehmen verwendet. Bereitstellung von Anweisungen für Microsoft-Teams Chatrooms Geräte wird unter [Konfigurieren einer Microsoft-Teams Chatrooms Konsole](console.md)behandelt. Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Online-Bereitstellung: vollständig auf Office 365-Umgebung Ihrer Organisation bereitgestellt wird. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms mit Office 365](with-office-365.md).
    
- Lokale Bereitstellung: Ihrer Organisation sind, die es verwaltet, Server, auf dem Active Directory, Exchange und Skype für Business Server gehostet werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms mit Skype für Business Server](with-skype-for-business-server-2015.md)
    
- Hybridbereitstellungen: Ihrer Organisation mit einer Kombination verschiedener Dienste, mit einigen gehostet an lokalen und der über Office 365 online gehostet. Mit Microsoft-Teams Räumen sind die folgenden hybridszenarien unterstützt: 
    
  - Exchange Online mit Skype für Business Server lokal. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms mit Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange lokal mit Microsoft-Teams oder Skype für Business Online. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms mit Exchange lokal (Hybrid)](with-exchange-on-premises.md).
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft-Teams Rooms "Gerät"Konto zugewiesen werden soll in Active Directory, Exchange und Skype für Unternehmen. Das Konto wird verwendet, um Zugriff auf die Besprechung Kalender und Einrichten von Microsoft-Teams oder Skype für Business Connectivity. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft-Teams Räume werden diese Besprechung teilnehmen und verschiedene Features für die Besprechungsteilnehmer bereitstellen können.
  
> [!IMPORTANT]
> Ohne ein Konto Gerät kann keine dieser Funktionen verwendet werden. 
  
Jedes Gerät Konto ist für ein einzelnes Gerät Microsoft Teams Chatrooms eindeutig und erfordert einige Setup:
  
- Das Gerät Konto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss konfiguriert werden, damit Microsoft Teams Chatrooms, um das Gerät Konto zu überprüfen und die entsprechenden Microsoft-Dienste zu erreichen können.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung. In hybridumgebungen benötigen das Konto für den Microsoft-Teams Chatrooms Kennwort Sync AAD synchron aktiviert werden, da Microsoft Teams Chatrooms Authentifizierung 0ffice 365 Authentifizierung erforderlich ist.
  
Von einem Gerät-Konto können als das Ressourcenkonto vorstellen, die Personen als einen des Raums oder eine Besprechung Konferenzraum des Kontos zu erkennen. Wenn Sie eine Besprechung in diesem Konferenzraum planen möchten, laden Sie das Konto zu dieser Besprechung ein. Um Microsoft Teams Chatrooms möglichst effektiv zu verwenden, führen Sie die gleiche mit dem Gerät-Konto, das jeweils zugeordnet ist.
  
Wenn Sie bereits über ein Postfach-Ressourcenkonto festgelegt haben Sie können dieses Ressourcenkontos für den Besprechungsraum, auf dem Microsoft-Teams Chatrooms installieren, ändern, ein Gerät berücksichtigt. Wenn das erledigt ist, müssen Sie, nur ein Microsoft-Teams Chatrooms Gerät das Gerät-Konto hinzuzufügen. Beispiele für Gerät Konto Setup finden Sie weiter unten.
  
Zusätzliche Konfiguration ist Remoteverwaltung möglich mit Microsoft Azure Monitor, wie beschrieben in [Planen der Microsoft Teams Chatrooms Management mit Azure Monitor](azure-monitor-plan.md), [Microsoft-Teams-Chatrooms bereitstellen Management mit Azure Monitor](azure-monitor-deploy.md)und [ Verwalten von Microsoft-Teams Chatrooms Geräte mit Azure Monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften darstellen, die Mindestkonfiguration für ein Konto Gerät Microsoft Teams Chatrooms entwickelt. Das Gerät Konto erfordert möglicherweise weitere Setup.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange-Postfach (Exchange 2013 SP1 oder höher, oder Exchange Online)  <br/> |Aktivieren das Konto mit einem Exchange-Postfach erhält das Gerät Konto die Fähigkeit zum Empfangen und Senden von e-Mail-Nachrichten und Besprechungsanfragen und um einen Kalender Besprechungen auf dem Gerät Microsoft Teams Räume anzuzeigen. Das Microsoft-Teams Chatrooms Postfach muss ein Raumpostfach sein.  <br/> |
|Skype für Unternehmen ist aktiviert.  <br/> |Skype für Unternehmen muss, um die verschiedenen Konferenzfunktionen, wie Videokonferenzen, Instant Messaging und Bildschirmfreigabe-verwenden aktiviert sein. Skype für Business Online und Skype für Business Server werden unterstützt.  <br/> |
|Kennwort aktiviert  <br/> |Das Gerät Konto muss mit einem Kennwort aktiviert werden, oder es kann nicht mit Exchange oder Skype für Business Server authentifizieren.  <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Während die Eigenschaften für die grundlegende Konfiguration das Gerät Konto in einer einfachen Umgebung eingerichtet werden zulässig, es ist möglich Ihrer Umgebung hat die anderen Einschränkungen auf Directory-Konten, die erfüllt sein müssen, Reihenfolge für Microsoft-Teams Chatrooms erfolgreich verwenden die Geräte-Account.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Zertifikate möglicherweise für Exchange und Skype für Business Server erforderlich. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |
   
Die einfachste Möglichkeit zum Einrichten von Konten Gerät ist von remote Windows PowerShell konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Gerät Konten erstellen, oder validate vorhandenen Ressourcenkonten, mit denen Sie, um Sie unterstützen sie zu kompatibel Microsoft Teams Chatrooms Gerät Konten verleihen helfen.
  
Wenn Sie die Benutzeroberfläche von Office 365 über Windows PowerShell-Cmdlets verwenden möchten, können einige Schritte manuell ausgeführt werden. Finden Sie unter [Erstellen eines Geräts-Kontos mithilfe von Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Siehe auch

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

