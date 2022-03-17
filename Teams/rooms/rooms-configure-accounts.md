---
title: Konfigurieren von Konten für Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: In diesem Thema erfahren Sie, wie Sie Konten für Microsoft Teams-Räume (einschließlich Surface Hub) und Telefonen vor Ort konfigurieren.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514730"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft Teams-Räume
 
In diesem Thema wird das Erstellen von Konten von Microsoft Teams-Räume. Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Onlinebereitstellung: Die Umgebung Ihrer Organisation wird ausschließlich nach Microsoft 365 Oder Office 365.
    
- Lokale Bereitstellung: Ihre Organisation verfügt über Server, die von ihr kontrolliert werden, wo Active Directory, Exchange und Skype for Business Server gehostet werden. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Hybridbereitstellungen: Ihre Organisation verfügt über eine Mischung aus Diensten, von den einige lokal gehostet werden und einige online über Microsoft 365 oder Office 365. Im Microsoft Teams-Räume werden die folgenden Hybridszenarien unterstützt:
    
  - Exchange Online mit Skype for Business Server lokal.
    
  - Exchange lokal mit Microsoft Teams.
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft Teams-Räume müssen ein "Ressourcenkonto" in Active Directory, Exchange und (falls erforderlich) Skype for Business. Das Konto wird verwendet, um auf den Besprechungskalender zu zugreifen und die Microsoft Teams und/oder Skype for Business herstellen. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft Teams-Räume können an dieser Besprechung teilnehmen und den Besprechungsteilnehmern verschiedene Funktionen zur Verfügung stellen.
  
> [!IMPORTANT]
> Ohne ein Ressourcenkonto funktioniert keine dieser Features.
  
Jedes Ressourcenkonto ist für eine einzelne Microsoft Teams-Räume-Installation eindeutig.
  
- Das Ressourcenkonto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss so konfiguriert werden, Microsoft Teams-Räume Benutzer das Überprüfen des Ressourcenkontos und das Erreichen der entsprechenden Microsoft-Dienste.

> [!NOTE] 
> Wenn Sie Microsoft Teams-Panels verwenden, meldet Teams-Räume-Ressourcenkonto sich sowohl bei den Teams-Räume als auch den zugeordneten Teams an.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung.
> 
In Hybridumgebungen, die keine Skype for Business, wird dringend empfohlen, das Konto systemeigene in einem Azure Active Directory. Wenn das Konto mit dem lokalen Active Directory erstellt werden muss, muss die Kennwortsynchronisierung in Azure Active Directory (AAD) Verbinden-Synchronisierung aktiviert werden, da für die Microsoft Teams-Räume-Authentifizierung ein Microsoft 365 oder Office 365 Authentifizierung. Stellen Sie beim Einrichten des Kontos sicher, dass die E-Mail-Adresse des Kontos mit dem Benutzerprinzipalnamen (User Principal Name, UPN) in der AAD. 
  
Sie können sich ein Ressourcenkonto als das Konto auskennen, das die Benutzer als den Namen eines Konferenzraums oder eines gemeinsam genutzten Raums erkennen. Wenn Sie eine Besprechung an diesem Platz planen möchten, laden Sie das Ressourcenkonto zu dieser Besprechung ein.
  
Wenn Sie bereits ein Exchange-Ressourcenpostfachkonto für den Speicherplatz eingerichtet haben, in dem Sie Microsoft Teams-Räume installieren, können Sie dieses Konto in ein Teams-Räume-Ressourcenkonto ändern. Sobald dies erfolgt ist, müssen Sie sich nur noch bei Microsoft Teams-Räume mit diesem Konto anmelden.
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften stellen die Mindestkonfiguration für ein Ressourcenkonto dar, mit dem sie Microsoft Teams-Räume. Ihr Ressourcenkonto erfordert möglicherweise eine weitere Einrichtung.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange Postfach (Exchange 2013 SP1 oder höher oder Exchange Online)  <br/> |Das Exchange ermöglicht dem Ressourcenkonto das Empfangen und Senden von E-Mails und Besprechungsanfragen sowie das Anzeigen eines Besprechungskalenders auf Microsoft Teams-Räume. Bei Microsoft Teams-Räume Postfach muss es sich um ein Ressourcenpostfach vom Typ "Raum" geben.  <br/> |
|Skype for Business ist aktiviert  <br/> |Skype for Business können aktiviert werden, um verschiedene Skype for Business-Konferenzfeatures wie Videoanrufe, Videoanrufe und Bildschirmfreigaben zu verwenden.  <br/> |
|Kennwort aktiviert  <br/> |Das Ressourcenkonto muss mit einem Kennwort aktiviert werden, oder es kann sich nicht mit Microsoft Teams, Exchange oder Skype for Business Server. Der Kennwortablauf muss für alle Teams-Räume deaktiviert sein.   <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Die Eigenschaften für die grundlegende Konfiguration ermöglichen zwar das Einrichten des Ressourcenkontos in einer einfachen Umgebung, es ist jedoch möglich, dass in Ihrer Umgebung weitere Einschränkungen hinsichtlich Konten gelten, die erfüllt werden müssen, damit Microsoft Teams-Räume das Ressourcenkonto erfolgreich verwenden kann.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Zertifikate sind möglicherweise sowohl für Exchange als Skype for Business Server. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |

## <a name="see-also"></a>Mehr dazu

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
