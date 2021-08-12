---
title: tblPrincipal
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
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.
ms.openlocfilehash: 50d20aee156a4a919effac26ff29c371ec2cf886c12300ecd07268576730ae49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338023"
---
# <a name="tblprincipal"></a>tblPrincipal
 
Die Tabelle „tblPrincipal“ enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Die Prinzipal-ID.  <br/> |
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Die GUID des Prinzipals. Dies wird allgemein als alternativer Primärschlüssel verwendet, da seine Bedeutung in den Active Directory Domain Services-Bereich übergeht. (Die GUID für einen zwischengespeicherten Prinzipal ist mit der entsprechenden Objekt-GUID in Active Directory identisch.)  <br/> |
|prinUri  <br/> |nvarchar (256), not null  <br/> |Der URI des Prinzipals. Für Benutzer wird das SIP-Schema verwendet, für fast alles andere das ma-grp-Schema.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Der allgemeine Name. Wird nur von Benutzertypen verwendet.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Der Anzeigename. Wird nur von Benutzertypen verwendet.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Der Firmenname. Wird nur von Benutzertypen verwendet.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Die E-Mail-Adresse. Wird nur von Benutzertypen verwendet.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Der Domänenname des Active Directory-Objekts, von dem der Prinzipal eine zwischengespeicherte Version ist. Kann für Typen, die keine Active Directory-Objekte sind (z. B. Systembenutzer), null sein.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Benutzerprinzipalname (UPN). Wird nur von regulären Benutzertypen verwendet.  <br/> |
|prinDisabled  <br/> |smallint, not null  <br/> | 0: Der Prinzipal ist aktiv. <br/>  1: Der Prinzipal ist deaktiviert, da die SIP-Funktionen des Benutzers deaktiviert sind. <br/>  2: Der Prinzipal wird gelöscht, da das zugehörige AD-Objekt gelöscht wird. <br/> |
|prinTypeID  <br/> |smallint, nicht NULL  <br/> |Der Prinzipaltyp (aus der Tabelle „tblPrincipalType“).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype for Business Clientpoolzuweisung für den Prinzipal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Der Richtlinienwert für den Server für beständigen Chat für den Benutzer, wenn eine Tagtyprichtlinie vorhanden ist.  <br/> |
|prinAddedBy  <br/> |Ganzzahl  <br/> |Die Prinzipal-ID des Erstellers.  <br/> |
|prinAddedOn  <br/> |bigint, not null  <br/> |Der Zeitstempel für den Zeitpunkt der Erstellung.  <br/> |
|prinUpdatedBy  <br/> |Ganzzahl  <br/> |Die ID des Prinzipals, der dieses Element zuletzt aktualisiert hat.  <br/> |
|prinUpdatedOn  <br/> |bigint, not null  <br/> |Der Zeitstempel für die letzte Aktualisierung.  <br/> |
|prinVerifiedOn  <br/> |datetime, not null  <br/> |Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Der Primärschlüssel.  <br/> |
|prinTypeID  <br/> |Fremdschlüssel mit Suche in der Tabelle „ tblPrincipalType.ptypeID“.  <br/> |
   

