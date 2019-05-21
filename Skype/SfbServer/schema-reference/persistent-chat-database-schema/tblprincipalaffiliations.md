---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295314"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Prinzipal-Nr  <br/> |int, nicht NULL  <br/> |Die ID des verbundenen Prinzipals.  <br/> |
|affiliationID  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der die Zuordnung darstellt. Jeder Prinzipal (mit Ausnahme von System-User-Typen) hat ebenfalls eine Selbstzuordnung.  <br/> |
|Index  <br/> |int, nicht NULL  <br/> |Index. Der Wert für Self-Affiliations ist-1, und für die anderen Zuordnungen wird er sequenziell von 1 innerhalb der einzelnen \<Prinzipal-affiliationId\> -Buckets erhöht.  <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |Prinzipal, der das neueste Update durchführte. Dies ist normalerweise 1, was bedeutet, dass die Active Directory-Synchronisierung erfolgt.  <br/> |
   
**Schlüssel**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|\<Prinzipal-, Index-, affiliationID\>  <br/> |Primärschlüssel  <br/> |
|Prinzipal-Nr  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
|affiliationID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
   

