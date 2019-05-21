---
title: Schema Änderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die von Skype for Business Server benötigt werden.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296658"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Schema Änderungen in Skype for Business Server
 
Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die von Skype for Business Server benötigt werden.

> [!NOTE]
> Wenn Sie ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchgeführt haben, werden keine Schemaänderungen vorgenommen, und daher gilt dieser Artikel nicht.
  
Für Skype for Business Server sind mehrere neue Klassen und Attribute erforderlich, und einige vorhandene Klassen und Attribute werden geändert. Darüber hinaus werden viele Konfigurationsinformationen für Skype for Business Server im zentralen Verwaltungsspeicher statt in AD DS gespeichert, wie in früheren Versionen. Die folgenden Informationen werden weiterhin in AD DS in Skype for Business Server gespeichert:
  
- **Schema Erweiterungen**:
    
  - Benutzerobjekterweiterungen
    
  - Erweiterungen für Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten vorherigen Versionen von lync Server.
    
- **Daten** (im erweiterten Schema von Skype for Business Server und in vorhandenen Schemaklassen gespeichert):
    
  - Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen
    
  - Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale
    
  - Ein Zeiger auf den zentralen Verwaltungsspeicher
    
  - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)
    
In diesem Thema werden die Active Directory-Schemaänderungen beschrieben, die von Skype for Business Server erforderlich sind. Es werden keine Schemaänderungen beschrieben, die in früheren Versionen von Office Communications Server eingeführt wurden. Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in Skype for Business Server](schema-classes-and-descriptions.md). Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute und Beschreibungen in Skype for Business Server](schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute nach Klasse in Skype for Business Server](schema-attributes-by-class.md).
  
Das Attribut msRTCSIP-Präfix identifiziert Klassen und Attribute, die für Skype for Business Server spezifisch sind.
  
## <a name="new-active-directory-attributes"></a>Neue Active Directory-Attribute

In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die von Skype for Business Server hinzugefügt werden.
  
**Von Skype for Business Server hinzugefügte Attribute**

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien. Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei. Dieses Attribut wird für Exchange 2013 freigegeben.  <br/> |
|Attribut msRTCSIP-UserRoutingGroupId  <br/> |Hierbei handelt es sich um die SIP-Routinggruppen-ID. Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.  <br/> |
|Attribut msRTCSIP-MirrorBackEndServer  <br/> |Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Geänderte Active Directory-Klassen

In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die von Skype for Business Server geändert werden.
  
**Von Skype for Business Server geänderte Klassen**

|**Klasse**|**Änderung**|**Klasse oder Attribut**|
|:-----|:-----|:-----|
|User  <br/> |Add: mayContain  <br/> Add: mayContain  <br/> |ProxyAddresses  <br/> Attribut msRTCSIP-UserRoutingGroupId  <br/> |
|Kontakt  <br/> |Add: mayContain  <br/> Add: mayContain  <br/> |ProxyAddresses  <br/> Attribut msRTCSIP-UserRoutingGroupId  <br/> |
|E-Mail-Empfänger  <br/> |Add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|Attribut msRTCSIP-GlobalTopologySetting  <br/> |Add: mayContain  <br/> |Attribut msRTCSIP-MirrorBackEndServer  <br/> |
   

