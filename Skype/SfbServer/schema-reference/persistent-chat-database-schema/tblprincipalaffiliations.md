---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations enthält die Prinzipalmitgliedschaften, die Mitgliedschaften an Speicherorten, einschließlich Active Directory Domain Services-Sicherheitsgruppen, in Active Directory-Containern, in Domänen beschreiben.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815865"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations enthält die Prinzipalmitgliedschaften, die Mitgliedschaften an Speicherorten, einschließlich Active Directory Domain Services-Sicherheitsgruppen, in Active Directory-Containern, in Domänen beschreiben.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|principalID  <br/> |int, nicht NULL  <br/> |ID des zugeordneten Prinzipals.  <br/> |
|affiliationID  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, die für die Zuordnung steht. Jeder Prinzipal (ausgenommen system-user-types) verfügt auch über eine Selbstzuordnung.  <br/> |
|Index  <br/> |int, nicht NULL  <br/> |Index. Der Wert für Selbstzugehörigkeiten ist -1, und für die anderen Zuordnungen erhöht er sich sequenziell von 1 innerhalb jedes \<principalID, affiliationId\> Buckets.  <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |Prinzipal, der die letzte Aktualisierung durchführte. Der Wert ist in der Regel 1, was der Active Directory-Synchronisierung entspricht.  <br/> |
   
**Keys**

|**Columns**|**Beschreibung**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Primärschlüssel  <br/> |
|principalID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle  <br/> |
|affiliationID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle  <br/> |
   

