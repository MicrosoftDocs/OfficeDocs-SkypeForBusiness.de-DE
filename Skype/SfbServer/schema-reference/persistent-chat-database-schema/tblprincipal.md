---
title: tblPrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: TblPrincipal enthält alle Prinzipale, einschließlich Benutzer, Ordner und Gruppen.
ms.openlocfilehash: adeb4e52ea9bd276de09d90945443431fb3be94f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880973"
---
# <a name="tblprincipal"></a>tblPrincipal
 
TblPrincipal enthält alle Prinzipale, einschließlich Benutzer, Ordner und Gruppen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|prinGuid  <br/> |GUID, nicht null  <br/> |Prinzipal-GUID. Im Allgemeinen gibt es wird als eine alternative Primärschlüssel verwendet, da seine Bedeutung über in den Active Directory-Domänendienste Platz schneidet. (Die GUID für eine Cache Prinzipal ist gleich dem entsprechenden Active Directory-Objekt-GUID.)  <br/> |
|prinUri  <br/> |Nvarchar (256), nicht null  <br/> |Prinzipal-URI. Das SIP-Schema für Benutzer verwendet wird, und Ma-Gruppe für fast alles verwendet wird.  <br/> |
|prinName  <br/> |Nvarchar (256)  <br/> |Allgemeiner Name. Nur vom Benutzertypen verwendet.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Anzeigename. Nur vom Benutzertypen verwendet.  <br/> |
|prinCompanyName  <br/> |Nvarchar (256)  <br/> |Name der Firma. Nur vom Benutzertypen verwendet.  <br/> |
|prinEmail  <br/> |Nvarchar (256)  <br/> |E-Mail. Nur vom Benutzertypen verwendet.  <br/> |
|prinADPath  <br/> |Nvarchar (384)  <br/> |Domänenname des Active Directory-Objekt, dem der Prinzipal eine zwischengespeicherte Version ist. Null kann für Typen sein, die nicht Active Directory-Objekte (beispielsweise Benutzer des Systems) sind.  <br/> |
|prinADUserPrincipalName  <br/> |Nvarchar (256)  <br/> |Des Benutzers Benutzerprinzipalnamen (UPN). Nur vom regulären Benutzertypen verwendet.  <br/> |
|prinDisabled  <br/> |Smallint, nicht null  <br/> | 0: Prinzipal ist aktiv. <br/>  1: Prinzipal ist deaktiviert, da die SIP-Funktionen des Benutzers deaktiviert sind. <br/>  2: Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wurde. <br/> |
|prinTypeID  <br/> |Smallint, nicht null  <br/> |Der Prinzipaltyp (aus der Tabelle "tblprincipaltype").  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype für Business-Client-poolzuordnung für den Prinzipal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Persistent Chat-Server-Richtlinienwert für Benutzer, wenn eine tagtyprichtlinie vorhanden ist.  <br/> |
|prinAddedBy  <br/> |int  <br/> |Prinzipal-ID des Erstellers.  <br/> |
|prinAddedOn  <br/> |Bigint, nicht null  <br/> |Zeitstempel für den Zeitpunkt der Erstellung.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID des Prinzipals dies der letzten Aktualisierung.  <br/> |
|prinUpdatedOn  <br/> |Bigint, nicht null  <br/> |Zeitstempel für die letzte Aktualisierung.  <br/> |
|prinVerifiedOn  <br/> |DateTime, nicht null  <br/> |Datum und Uhrzeit der letzten Active Directory-Synchronisierung für den Prinzipal zu aktualisieren.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel.  <br/> |
|prinTypeID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblprincipaltype.ptypeid".  <br/> |
   

