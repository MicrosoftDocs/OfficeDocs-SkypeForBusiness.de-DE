---
title: Änderungen, die von Grant-CsOUPermission in Skype for Business Server vorgenommen werden
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Zum Delegieren der Skype for Business Server-Verwaltung können Sie bestimmten Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der universellen RtC-Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, auf die Organisationseinheiten zugreifen können, ohne Mitglied der Gruppe "Domänen-Admins" zu sein.
ms.openlocfilehash: 09a6d6baf554b18db0a388619ffb74c85c6963fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831845"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Änderungen, die von Grant-CsOUPermission in Skype for Business Server vorgenommen werden
 
Zum Delegieren der Skype for Business Server-Verwaltung können Sie bestimmten Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der universellen RtC-Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, auf die Organisationseinheiten zugreifen können, ohne Mitglied der Gruppe "Domänen-Admins" zu sein. 
  
Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.
  
## <a name="granting-permission-for-user-objects"></a>Erteilen von Berechtigungen für User-Objekte

Wenn Sie das **Grant-CsOuPermission-Cmdlet** für Benutzerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>User</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete User-Objekte  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Erteilen von Berechtigungen für Computer-Objekte

Wenn Sie das **Grant-CsOuPermission-Cmdlet** für Computerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Computer</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Read Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Untergeordnete Computer-Objekte  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Erteilen von Berechtigungen für Contact oder AppContact-Objekte

Wenn Sie das **Grant-CsOuPermission-Cmdlet** für Kontaktobjekte oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Contact</c0>- oder <c1>AppContact</c1>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read Personal-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Erteilen von Berechtigungen für Device-Objekte

Wenn Sie das **Grant-CsOuPermission-Cmdlet** für Geräteobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>Device</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Public-Information  <br/> Read Personal-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete Contact-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Untergeordnetes Element erstellen  <br/> Untergeordnetes Element löschen  <br/> Struktur löschen  <br/> |Kontakt  <br/> |
|RTCUniversalUserAdmins  <br/> |Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> |Untergeordnete User-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Write description  <br/> Write telephoneNumber  <br/> Write msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete Contact-Objekte  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Erteilen von Berechtigungen für InetOrgPerson-Objekte

Wenn Sie das **Grant-CsOuPermission-Cmdlet** für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.
  
**Für <c0>InetOrgPerson</c0>-Objekte erteilte Berechtigungen**

|**Gruppe**|**Berechtigung**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Verzeichnisänderungen replizieren  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Inhalt auflisten  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Read Personal-Information  <br/> Read Public-Information  <br/> Read General-Information  <br/> Read User-Account-Restrictions  <br/> |Untergeordnete inetOrgPerson-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Write proxyAddresses  <br/> |Untergeordnete inetOrgPerson-Objekte  <br/> |
   

