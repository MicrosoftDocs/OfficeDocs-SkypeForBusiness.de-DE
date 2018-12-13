---
title: Schemaänderungen in Skype für Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Vor der Bereitstellung und Betrieb von Skype für Business Server müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten. Durch die schemaerweiterungen hinzufügen die Klassen und Attribute, die von Skype für Business Server erforderlich sind.
ms.openlocfilehash: 8594ff3a25c7af7ef8c57468a8900d3abbb7f790
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240917"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Schemaänderungen in Skype für Business Server
 
Vor der Bereitstellung und Betrieb von Skype für Business Server müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten. Durch die schemaerweiterungen hinzufügen die Klassen und Attribute, die von Skype für Business Server erforderlich sind.

> [!NOTE]
> Wenn Sie von Lync Server 2013 auf Skype für Business Server 2015 durchführen, werden keine schemaänderungen vorgenommen, und daher in diesem Artikel wird nicht angewendet.
  
Skype für Business Server erfordert einige neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute. Darüber hinaus wird wie in früheren Versionen viel Konfigurationsinformationen für Skype für Business Server in der zentralen Verwaltungsspeichers statt in AD DS gespeichert. Die folgende Informationen wird weiterhin in AD DS in Skype für Business Server gespeichert:
  
- **Schemaerweiterungen**:
    
  - Benutzerobjekterweiterungen
    
  - Erweiterungen für Klassen zum Aufrechterhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen von Lync Server.
    
- **Daten** (gespeichert in Skype für erweiterte Business Server-Schema und in vorhandenen Schemaklassen):
    
  - Benutzer SIP-URI Uniform Resource Identifier () und andere Einstellungen
    
  - Kontaktobjekte für Anwendungen wie Reaktionsgruppe und die Konferenzzentrale
    
  - Ein Zeiger auf den zentralen Verwaltungsspeicher
    
  - Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)
    
In diesem Thema werden die Active Directory-schemaänderungen von Skype für Business Server erforderlich. Es wird nicht schemaänderungen beschrieben, die durch frühere Versionen von Office Communications Server eingeführt wurden. Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schemaklassen und Beschreibungen in Skype für Business Server](schema-classes-and-descriptions.md). Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schemaattribute und Beschreibungen in Skype für Business Server](schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen können sie enthalten, finden Sie unter [Schemaattribute nach Klasse in Skype für Business Server](schema-attributes-by-class.md).
  
Das Präfix "MsRTCSIP" identifiziert Klassen und Attribute, die speziell für Skype für Business Server sind.
  
## <a name="new-active-directory-attributes"></a>Neue Active Directory-Attribute

Die folgende Tabelle beschreibt die Active Directory-Attribute, die von Skype für Business Server hinzugefügt werden.
  
**Skype für Business Server hinzugefügte Attribute**

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Dieses mehrwertige Attribut enthält Bezeichner für Richtlinien enthalten, die für den Benutzer gelten. Halten Sie, dass Richtlinien für die Dauer des Haltestatus Postfachelemente für den Benutzer beibehalten. Dieses Attribut ist für Exchange 2013 freigegeben.  <br/> |
|MsRTCSIP-UserRoutingGroupId  <br/> |Hierbei handelt es sich um die SIP-routing Gruppen-ID. Benutzer in der gleichen Gruppe werden auf dem gleichen Front-End-Server registriert.  <br/> |
|MsRTCSIP-MirrorBackEndServer  <br/> |Dieses Attribut wird zum Speichern der gespiegelten SQL Server-Back-End von den Front-End-Pool verwendet.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Geänderte Active Directory-Klassen

Die folgende Tabelle beschreibt die Active Directory-Klassen, die von Skype für Business Server geändert werden.
  
**Von Skype für Business Server geänderte Klassen**

|**Klasse**|**Änderung**|**Klasse oder eines Attributs**|
|:-----|:-----|:-----|
|Benutzer  <br/> |hinzufügen: MayContain  <br/> hinzufügen: MayContain  <br/> |ProxyAddresses  <br/> MsRTCSIP-UserRoutingGroupId  <br/> |
|Kontakt  <br/> |hinzufügen: MayContain  <br/> hinzufügen: MayContain  <br/> |ProxyAddresses  <br/> MsRTCSIP-UserRoutingGroupId  <br/> |
|E-Mail-Empfänger  <br/> |hinzufügen: MayContain  <br/> |msExchUserHoldPolicies  <br/> |
|MsRTCSIP-GlobalTopologySetting  <br/> |hinzufügen: MayContain  <br/> |MsRTCSIP-MirrorBackEndServer  <br/> |
   

