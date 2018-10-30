---
title: 'Lync Server 2013: Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto'
TOCTitle: Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412870(v=OCS.15)
ms:contentKeyID: 49295146
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2010-11-03_

Nach dem Erstellen des Computerobjekts für das Kerberos-Authentifizierungskonto können Sie das Kennwort für das Konto einrichten. Zum Festlegen des Kennworts des Kerberos-Kontos auf einem Server führen Sie das Windows PowerShell-Cmdlet aus. Sie können das Kennwort für das Objekt festlegen, das Sie für die Kerberos-Authentifizierung erstellt haben. Das Kennwort kann auf einen bekannten Wert festgelegt werden, ist aber standardmäßig ein beliebiges Kennwort. Das Kennwort steht allen Kerberos-Authentifizierungsquellen zur Verfügung, die dieses Konto verwenden. Kerberos-Kontokennwörter werden mit Windows PowerShell-Cmdlets eingerichtet und verwaltet.


> [!NOTE]
> Das Kerberos-Kontoobjekt ist ein Computerobjekt, verwendet aber für Vorgänge in den Windows PowerShell-Cmdlets, auf die verwiesen wird, den Parameter "UserAccount". Beachten Sie, dass dies kein Fehler, sondern das beabsichtigte Verhalten des Cmdlets ist, wenn es für die Erstellung und Verwaltung von Kerberos-Konten verwendet wird.



## In diesem Abschnitt

  - [Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS in Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

