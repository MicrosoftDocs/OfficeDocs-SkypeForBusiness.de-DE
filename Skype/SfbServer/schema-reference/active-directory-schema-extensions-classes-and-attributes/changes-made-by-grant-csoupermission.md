---
title: Von Grant-CsOUPermission in Skype for Business Server vorgenommene Änderungen
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Wenn Sie die Skype for Business Server-Verwaltung delegieren möchten, können Sie den angegebenen Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC universelle Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815523"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Von Grant-CsOUPermission in Skype for Business Server vorgenommene Änderungen
 
Wenn Sie die Skype for Business Server-Verwaltung delegieren möchten, können Sie den angegebenen Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC universelle Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein. 
  
Das Cmdlet **Grant-CsOuPermission** gewährt den Objekten in der angegebenen OU Berechtigungen, wie in den folgenden Tabellen angegeben.
  
## <a name="granting-permission-for-user-objects"></a>Erteilen der Berechtigung für Benutzerobjekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für Benutzerobjekte gewährte Berechtigungen**

|**Gruppe**|**Berechtigungs**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replizieren von Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Lesen von RTCUserSearchPropertySet  <br/> Lesen von RTCUserProvisioningPropertySet  <br/> Lesen von RTCPropertySet  <br/> Lesen öffentlicher Informationen  <br/> Allgemeine Informationen lesen  <br/> Lesen von Benutzerkonto Einschränkungen  <br/> |Nachfolger Benutzerobjekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben von msExchUCVoiceMailSettings  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> Schreiben von proxyAddresses  <br/> |Nachfolger Benutzerobjekte  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Erteilen der Berechtigung für Computer Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für Computer Objekte gewährte Berechtigungen**

|**Gruppe**|**Berechtigungs**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replizieren von Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Lesen öffentlicher Informationen  <br/> Read validiert-DNS-Host-Name  <br/> |Nachfolger Computer Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Lesen öffentlicher Informationen  <br/> Read validiert-DNS-Host-Name  <br/> |Nachfolger Computer Objekte  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Erteilen der Berechtigung für Kontakt-oder AppContact-Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für Contact-oder AppContact-Objekte gewährte Berechtigungen**

|**Gruppe**|**Berechtigungs**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replizieren von Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Lesen von RTCUserSearchPropertySet  <br/> Lesen von RTCUserProvisioningPropertySet  <br/> Lesen von RTCPropertySet  <br/> Lesen öffentlicher Informationen  <br/> Allgemeine Informationen lesen  <br/> Lesen persönlicher Informationen  <br/> Lesen von Benutzerkonto Einschränkungen  <br/> |Nachfolger-Kontaktobjekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben von otherIpPhone  <br/> Schreiben von DisplayName  <br/> Beschreibung schreiben  <br/> Schreiben von telephoneNumber  <br/> Schreiben von msExchUCVoiceMailSettings  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> Schreiben von proxyAddresses  <br/> |Nachfolger-Kontaktobjekte  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Erteilen der Berechtigung für Geräteobjekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Geräteobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für Geräteobjekte gewährte Berechtigungen**

|**Gruppe**|**Berechtigungs**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replizieren von Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Lesen von RTCUserSearchPropertySet  <br/> Lesen von RTCUserProvisioningPropertySet  <br/> Lesen von RTCPropertySet  <br/> Lesen öffentlicher Informationen  <br/> Lesen persönlicher Informationen  <br/> Allgemeine Informationen lesen  <br/> Lesen von Benutzerkonto Einschränkungen  <br/> |Nachfolger-Kontaktobjekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Erstellen eines untergeordneten Elements  <br/> Untergeordnetes Element löschen  <br/> Struktur löschen  <br/> |Kontakt  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von DisplayName  <br/> Beschreibung schreiben  <br/> Schreiben von telephoneNumber  <br/> |Nachfolger Benutzerobjekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben von otherIpPhone  <br/> Schreiben von DisplayName  <br/> Beschreibung schreiben  <br/> Schreiben von telephoneNumber  <br/> Schreiben von msExchUCVoiceMailSettings  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> Schreiben von proxyAddresses  <br/> |Nachfolger-Kontaktobjekte  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Erteilen der Berechtigung für InetOrgPerson-Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.
  
**Für InetOrgPerson-Objekte gewährte Berechtigungen**

|**Gruppe**|**Berechtigungs**|**Gilt für**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replizieren von Verzeichnisänderungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Listeninhalt  <br/> Alle Eigenschaften lesen  <br/> Leseberechtigungen  <br/> |Nur dieses Objekt  <br/> |
|RTCUniversalUserReadOnlyGroup hinzugefügt  <br/> |Lesen von RTCUserSearchPropertySet  <br/> Lesen von RTCUserProvisioningPropertySet  <br/> Lesen von RTCPropertySet  <br/> Lesen persönlicher Informationen  <br/> Lesen öffentlicher Informationen  <br/> Allgemeine Informationen lesen  <br/> Lesen von Benutzerkonto Einschränkungen  <br/> |Nachgeordnete InetOrgPerson-Objekte  <br/> |
|RTCUniversalUserAdmins  <br/> |Schreiben von RTCUserSearchPropertySet  <br/> Schreiben von RTCUserProvisioningPropertySet  <br/> Schreiben von RTCPropertySet  <br/> Schreiben von proxyAddresses  <br/> |Nachgeordnete InetOrgPerson-Objekte  <br/> |
   

