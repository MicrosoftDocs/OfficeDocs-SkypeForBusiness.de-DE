---
title: 'Lync Server 2013: Schützen von IIS'
TOCTitle: Schützen von IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518332(v=OCS.15)
ms:contentKeyID: 60476347
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schützen von IIS in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

In Microsoft Office Communications Server 2007 und Microsoft Office Communications Server 2007 R2 wurden die Internetinformationsdienste (IIS) unter einem Standardbenutzerkonto ausgeführt. Dies konnte potenziell Probleme mit sich bringen: Bei Ablauf des zugehörigen Kennworts gingen möglicherweise Ihre Webdienste verloren und dieses Problem war häufig nur schwer zu diagnostizieren. Um die durch abgelaufene Kennwörter verursachten Probleme zu vermeiden, können Sie mit Microsoft Lync Server 2013 ein Computerkonto (für einen Computer, den es eigentlich nicht gibt) erstellen, das als Authentifizierungsprinzipal für alle Computer an einem Standort fungiert, auf denen IIS ausgeführt wird. Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden sie als Kerberos-Konten und der neue Authentifizierungsprozess als Kerberos-Webauthentifizierung bezeichnet. Auf diese Weise können Sie alle IIS-Server über ein einziges Konto verwalten.

Damit Sie Ihre Server unter diesem Authentifizierungsprinzipal ausführen können, müssen Sie zunächst mit dem Cmdlet "New-CsKerberosAccount" ein Computerkonto erstellen. Dieses Konto wird dann einem oder mehreren Standorten zugewiesen. Nach der Zuweisung wird die Zuordnung zwischen dem Konto und dem Lync Server 2013-Standort durch Ausführen des Cmdlets "Enable-CsTopology" aktiviert. Damit wird unter anderem der erforderliche Dienstprinzipalname (Service Principal Name, SPN) in den Active Directory-Verbunddiensten erstellt. Mithilfe von SPNs können Clientanwendungen einen bestimmten Dienst finden. Ausführliche Informationen finden Sie unter [New-CsKerberosAccount](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsKerberosAccount) in der Betriebsdokumentation.

## Bewährte Methoden

Für eine höhere IIS-Sicherheit wird empfohlen, ein Kerberos-Konto für IIS zu implementieren. Wenn Sie kein Kerberos-Konto implementieren, wird IIS unter einem Standardbenutzerkonto ausgeführt.

