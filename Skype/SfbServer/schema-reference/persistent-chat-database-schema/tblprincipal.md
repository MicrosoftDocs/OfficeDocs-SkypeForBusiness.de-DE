---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.
ms.openlocfilehash: 7924c65745e29cce6dd71dc14b1ecfe7b41fe8b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814503"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal enthält alle Prinzipale, einschließlich Benutzern, Ordnern und Gruppen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID. Dies wird im Allgemeinen als alternativer Primärschlüssel verwendet, da dessen Bedeutung in den Bereich der Active Directory-Domänendienste überschritten wird. (Die GUID für einen zwischengespeicherten Prinzipal entspricht der entsprechenden GUID des Active Directory-Objekts.)  <br/> |
|prinUri  <br/> |nvarchar (256); nicht NULL  <br/> |Prinzipal-URI. Das SIP-Schema wird für Benutzer verwendet, und MA-GRP wird für fast alles andere verwendet.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Allgemeiner Name Wird nur von Benutzertypen verwendet.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Anzeigename Wird nur von Benutzertypen verwendet.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Name des Unternehmens. Wird nur von Benutzertypen verwendet.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |E-Mail. Wird nur von Benutzertypen verwendet.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Der Domänenname des Active Directory-Objekts, in dem der Prinzipal eine zwischengespeicherte Version von ist. Kann NULL für Typen sein, die keine Active Directory-Objekte (wie Systembenutzer) sind.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Benutzerprinzipalname (User Principal Name, UPN) des Benutzers. Wird nur von normalen Benutzertypen verwendet.  <br/> |
|prinDisabled  <br/> |smallint, nicht NULL  <br/> | 0: Principal ist aktiv. <br/>  1: Principal ist deaktiviert, da die SIP-Funktionen des Benutzers deaktiviert sind. <br/>  2: Principal wird gelöscht, weil das zugeordnete anzeigen Objekt gelöscht wurde. <br/> |
|prinTypeID  <br/> |smallint, nicht NULL  <br/> |Principal Type (aus tblPrincipalType-Tabelle).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype for Business-Client Poolzuordnung für den Prinzipal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Server Richtlinienwert des beständigen Chats für Benutzer, wenn die Kategorie-typrichtlinie vorhanden ist.  <br/> |
|prinAddedBy  <br/> |int  <br/> |Prinzipal-ID des Erstellers.  <br/> |
|prinAddedOn  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für die Erstellungszeit.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |Die ID des Prinzipals, der diesen zuletzt aktualisiert hat.  <br/> |
|prinUpdatedOn  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für das letzte Update.  <br/> |
|prinVerifiedOn  <br/> |DateTime, nicht NULL  <br/> |Datum und Uhrzeit der letzten Aktualisierung der Active Directory-Synchronisierung für den Prinzipal.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel  <br/> |
|prinTypeID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipalType. ptypeID-Tabelle.  <br/> |
   

