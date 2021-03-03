---
title: Schemaänderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie active Directory Domain Services vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für Skype for Business Server erforderlich sind.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813575"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Schemaänderungen in Skype for Business Server
 
Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie active Directory Domain Services vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für Skype for Business Server erforderlich sind.

> [!NOTE]
> Wenn Sie ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 durchführen, werden keine Schemaänderungen vorgenommen, daher gilt dieser Artikel nicht.
  
Skype for Business Server erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute. Darüber hinaus werden viele Konfigurationsinformationen für Skype for Business Server im zentralen Verwaltungsspeicher und nicht wie in früheren Versionen in AD DS gespeichert. Die folgenden Informationen werden weiterhin in AD DS in Skype for Business Server gespeichert:
  
- **Schemaerweiterungen**:
    
  - Benutzerobjekterweiterungen
    
  - Erweiterungen für Klassen zur Aufrechterhaltung der Abwärtskompatibilität mit unterstützten früheren Versionen von Lync Server.
    
- **Daten** (gespeichert im erweiterten Skype for Business Server-Schema und in vorhandenen Schemaklassen):
    
  - Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen
    
  - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
  - Ein Verweis auf den zentralen Verwaltungsspeicher
    
  - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)
    
In diesem Thema werden die Active Directory-Schemaänderungen beschrieben, die für Skype for Business Server erforderlich sind. Schemaänderungen, die in früheren Versionen von Office Communications Server eingeführt wurden, werden nicht beschrieben. Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schemaklassen und Beschreibungen in Skype for Business Server](schema-classes-and-descriptions.md). Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schemaattribute und Beschreibungen in Skype for Business Server](schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen, die sie enthalten können, finden Sie unter [Schemaattribute nach Klasse in Skype for Business Server](schema-attributes-by-class.md).
  
Das Präfix "msRTCSIP" identifiziert Klassen und Attribute, die für Skype for Business Server spezifisch sind.
  
## <a name="new-active-directory-attributes"></a>Neue Active Directory-Attribute

In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die von Skype for Business Server hinzugefügt werden.
  
**Von Skype for Business Server hinzugefügte Attribute**

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten. Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert. Dieses Attribut wird für Exchange 2013 freigegeben.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Dieses Attribut wird verwendet, um das gespiegelte SQL Server, das vom Front-End-Pool verwendet wird, zu speichern.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Geänderte Active Directory-Klassen

In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die von Skype for Business Server geändert werden.
  
**Von Skype for Business Server geänderte Klassen**

|**Klasse**|**Ändern**|**Klasse oder Attribut**|
|:-----|:-----|:-----|
|Benutzer  <br/> |Hinzugefügt: mayContain  <br/> Hinzugefügt: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Kontakt  <br/> |Hinzugefügt: mayContain  <br/> Hinzugefügt: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Hinzugefügt: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

