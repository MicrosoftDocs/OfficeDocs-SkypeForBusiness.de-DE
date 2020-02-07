---
title: Konfigurieren von Konten für Microsoft Teams-Chatrooms
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: In diesem Thema finden Sie Informationen zum Konfigurieren von Konten für Microsoft Teams Rooms in Exchange und Skype for Business.
ms.openlocfilehash: 66eecbb0773f04599a0b5255cb5f83f158eb74f7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825943"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft Teams-Chatrooms
 
In diesem Thema finden Sie Informationen zu den Microsoft Teams-Räumen und deren Integration in Exchange und Skype for Business.
  
In diesem Thema wird erläutert, wie Sie Konten erstellen, die von Microsoft Teams Rooms in Microsoft Exchange und Skype for Business verwendet werden. Bereitstellungsanweisungen für Microsoft Teams rooms-Geräte finden Sie unter [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md). Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Online Bereitstellung: die Umgebung Ihres Unternehmens ist vollständig auf Office 365 bereitgestellt. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Office 365](with-office-365.md).
    
- Lokale Bereitstellung: Ihre Organisation verfügt über Server, die Sie steuert, wobei Active Directory, Exchange und Skype for Business Server gehostet werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Chatrooms mit Skype for Business Server](with-skype-for-business-server-2015.md) .
    
- Hybrid Bereitstellungen: Ihre Organisation verfügt über eine Kombination von Diensten, wobei einige lokal gehostet werden und einige Online über Office 365 gehostet werden. Bei Microsoft Teams-Räumen werden die folgenden Hybrid Szenarien unterstützt: 
    
  - Exchange Online mit Skype for Business Server lokal. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange lokal mit Microsoft Teams oder Skype for Business Online. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Exchange lokal (Hybrid)](with-exchange-on-premises.md).
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft Teams-Räumen muss ein "Geräte Konto" in Active Directory, Exchange und Skype for Business zugewiesen sein. Das Konto wird verwendet, um auf seinen Besprechungs Kalender zuzugreifen und Microsoft Teams oder Skype for Business-Konnektivität einzurichten. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft Teams-Chatrooms können an dieser Besprechung teilnehmen und den Besprechungsteilnehmern verschiedene Funktionen zur Verfügung stellen.
  
> [!IMPORTANT]
> Ohne ein Geräte Konto kann keines dieser Features funktionieren. 
  
Jedes Geräte Konto ist für ein einzelnes Microsoft Teams rooms-Gerät eindeutig und erfordert ein Setup:
  
- Das Geräte Konto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss so konfiguriert sein, dass Microsoft Teams-Chatrooms das Geräte Konto überprüfen und die entsprechenden Microsoft-Dienste erreichen können.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung. In Hybrid Umgebungen muss für das für Microsoft Teams verwendete Konto die Kennwortsynchronisierung in Aad-Synchronisierung aktiviert sein, da für die Authentifizierung in Microsoft Teams rooms die Office 365-Authentifizierung erforderlich ist.
  
Sie können sich ein Geräte Konto als das Ressourcenkonto vorstellen, das Personen als Besprechungsraum-oder Besprechungsraum Konto erkennen. Wenn Sie eine Besprechung in diesem Konferenzraum planen möchten, laden Sie das Konto zu dieser Besprechung ein. Damit Sie die Microsoft Teams-Räume am effektivsten nutzen können, gehen Sie mit dem Geräte Konto um, das jedem zugewiesen ist.
  
Wenn Sie bereits ein Ressourcen Postfachkonto für den Besprechungsbereich eingerichtet haben, in dem Sie Microsoft Teams-Räume installieren, können Sie dieses Ressourcenkonto in ein Geräte Konto ändern. Anschließend müssen Sie lediglich das Geräte Konto zu einem Microsoft Teams rooms-Gerät hinzufügen. Weitere Informationen finden Sie unter Geräte Konto-Setup Beispiele weiter unten.
  
Mit zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie in [Plan Microsoft Teams rooms Management with Azure Monitor](azure-monitor-plan.md)beschrieben, [Bereitstellen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-deploy.md)und [Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften stellen die Mindestkonfiguration für ein Geräte Konto für die Arbeit mit Microsoft Teams-Räumen dar. Für Ihr Geräte Konto ist möglicherweise ein weiteres Setup erforderlich.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange-Postfach (Exchange 2013 SP1 oder höher oder Exchange Online)  <br/> |Durch das Aktivieren des Kontos mit einem Exchange-Postfach erhält das Geräte Konto die Möglichkeit, sowohl e-Mail-Nachrichten und Besprechungsanfragen zu empfangen und zu senden als auch einen Besprechungs Kalender auf dem Microsoft Teams rooms-Gerät anzuzeigen. Das Microsoft Teams rooms-Postfach muss ein Raumpostfach sein.  <br/> |
|Skype for Business ist aktiviert  <br/> |Skype for Business muss aktiviert sein, um verschiedene Konferenzfunktionen wie Videoanrufe, Chats und Bildschirmübertragung verwenden zu können. Skype for Business Online und Skype for Business Server werden unterstützt.  <br/> |
|Kennwort aktiviert  <br/> |Das Geräte Konto muss mit einem Kennwort aktiviert sein, oder es kann nicht mit Exchange oder Skype for Business Server authentifiziert werden.  <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Während die Eigenschaften für die grundlegende Konfiguration zulassen, dass das Geräte Konto in einer einfachen Umgebung eingerichtet wird, ist es möglich, dass Ihre Umgebung andere Einschränkungen für Verzeichnis Konten aufweist, die erfüllt sein müssen, damit Microsoft Teams rooms die erfolgreiche Verwendung der Geräte Konto.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Möglicherweise sind Zertifikate sowohl für Exchange als auch für Skype for Business Server erforderlich. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |
   
Die einfachste Möglichkeit, Geräte Konten einzurichten, besteht darin, Sie mithilfe der Remote-Windows PowerShell zu konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Geräte Konten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Geräte Konten machen können.
  
Wenn Sie die Office 365-Benutzeroberfläche über Windows PowerShell-Cmdlets verwenden möchten, können einige Schritte manuell ausgeführt werden. Weitere Informationen finden Sie unter [Erstellen eines Geräte Kontos mit Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Siehe auch

[Planen von Microsoft Teams-Räumen](rooms-plan.md)
  
[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](rooms-manage.md)

