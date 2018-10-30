---
title: 'Lync Server 2013: Vorbereiten von Domänen'
TOCTitle: Vorbereiten von Domänen
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398721(v=OCS.15)
ms:contentKeyID: 49294721
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten von Domänen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Die Domänenvorbereitung ist der abschließende Schritt bei der Vorbereitung von Active Directory-Domänendienste für Lync Server 2013. Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.

Sie können die Domänenvorbereitung auf einem beliebigen Computer in der Domäne ausführen, in der Lync Server bereitgestellt wird. Sie müssen alle Domänen vorbereiten, auf denen Lync Server-Computer oder -Benutzer gehostet werden.

Wenn die Berechtigungsvererbung oder Berechtigungen für authentifizierte Benutzer in der Organisation deaktiviert wurden, sind während der Domänenvorbereitung zusätzliche Schritte erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Wenn in Ihrer Organisation anstelle der drei integrierten Container (für Benutzer, Computer und Domänencontroller) Organisationseinheiten verwendet werden, muss die Gruppe der authentifizierten Benutzer über Lesezugriff für die Organisationseinheiten verfügen. Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich. Wenn die Gruppe der authentifizierten Benutzer nicht über Lesezugriff auf die Organisationseinheit verfügt, führen Sie das Cmdlet **Grant-CsOuPermission** wie im folgenden Codebeispiel gezeigt aus, um Leseberechtigungen für die einzelnen Organisationseinheiten zu gewähren.

    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 

   &nbsp;

    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"

Ausführliche Informationen zur Verwendung des **Grant-CsOuPermission**-Cmdlets finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


> [!TIP]
> Ausführliche Informationen zu den ACEs, die im Domänenstamm und in den Benutzer-, Computer- und Domänencontrollercontainern erstellt werden, finden Sie unter <A href="lync-server-2013-changes-made-by-domain-preparation.md">Änderungen bei der Domänenvorbereitung in Lync Server 2013</A>.



## In diesem Abschnitt

  - [Ausführen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

