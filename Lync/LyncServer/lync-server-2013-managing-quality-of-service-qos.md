---
title: Verwalten der Dienstqualität (Quality of Service, QoS)
TOCTitle: Verwalten der Dienstqualität (Quality of Service, QoS)
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg405409(v=OCS.15)
ms:contentKeyID: 49295054
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Dienstqualität (Quality of Service, QoS)

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren, Die Dienstqualität stellt für Administratoren eine Möglichkeit dar, um Paketen mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.


> [!NOTE]
> In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router zwar für die Unterstützung der Paketmarkierung, Sie konfigurieren diese Geräte jedoch für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass sie auf dieselbe Art und Weise wie der Dienst in Ihrem Netzwerk konfiguriert ist.



Die Dienstqualität ist für Microsoft Lync Server 2013 nicht erforderlich. Wenn Sie QoS derzeit nicht verwenden, ist die Installation des Diensts vor dem Installieren von Lync Server 2013 nicht erforderlich. Wenn Sie in Ihrem Netzwerk erhebliche Paketverluste zu verzeichnen haben, wird empfohlen, dieses Problem durch Hinzufügen zusätzlicher Bandbreite abzuschwächen. Wenn keine zusätzliche Bandbreite hinzugefügt werden kann, können Sie stattdessen die Dienstqualität implementieren.

Lync Server 2013 bietet vollständige Unterstützung für die Dienstqualität. Demnach können Organisationen, in denen QoS bereits verwendet wird, Lync Server problemlos in die vorhandene Netzwerkinfrastruktur integrieren. Dazu müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS für Windows-fremde Geräte](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie Lync Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, kann das Produkt normalerweise nicht zum Ändern der von diesen Geräten verwendeten DSCP-Codes genutzt werden.

  - [Konfigurieren von Portbereichen für Konferenz-, Anwendungs- und Vermittlungsserver](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. In Lync Server 2013 wird die Dienstqualität nicht aktiviert oder deaktiviert, indem Sie beispielsweise einen Eigenschaftswert auf "True" oder "False" festlegen. Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert. Wenn Sie sich später dazu entschließen, QoS nicht zu verwenden, können Sie die Dienstqualität einfach durch Entfernen der entsprechenden Gruppenrichtlinienobjekte "deaktivieren".

  - [Konfigurieren von Portbereichen für Edgeserver](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren.

  - [Konfigurieren von Portbereichen für Microsoft Lync-Clients](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Diese Portbereiche gelten nur für Clientcomputer und stimmen in der Regel nicht mit den auf Ihren Servern konfigurierten Portbereichen überein.

  - [Konfigurieren einer QoS-Richtlinie für Konferenz-, Anwendungs- und Vermittlungsserver in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Mithilfe dieser Richtlinien werden die DSCP-Codes ermittelt, die auf verschiedene Pakettypen angewendet werden.

  - [Konfigurieren einer QoS-Richtlinie für A/V-Edgeserver](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Dieser Vorgang sollte nur für die interne Seite Ihrer Edgeserver ausgeführt werden. Die Ursache dafür ist, dass die Dienstqualität nicht für die Verwendung im Internet, sondern in Ihrem internen Netzwerk konzipiert ist.

  - [Konfigurieren von QoS-Richtlinien für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Beachten Sie, dass Microsoft Lync Server 2013 QoS für andere Windows-Betriebssysteme wie Windows Vista oder Windows XP nicht unterstützt.

  - [Konfigurieren von QoS (Quality of Service) auf Geräten mit Microsoft Lync Phone Edition](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Standardmäßig ist QoS für Lync Phone Edition-Geräte aktiviert. Sie können jedoch den DSCP-Standardwert ändern, um sicherzustellen, dass für alle Audiopakete in Ihrer Organisation derselbe DSCP-Code verwendet wird.


> [!NOTE]
> Wenn Sie Microsoft Windows Server&nbsp;2012 oder Windows Server 2012 R2 verwenden, haben Sie möglicherweise Interesse an der neuen Sammlung von Windows PowerShell-cmdlets, die für die Verwaltung der Dienstqualität auf dieser Plattform zur Verfügung stehen. Weitere Informationen finden Sie im Thema „Cmdlets für den Netzwerkqualitätsdienst in Windows PowerShell“ unter <A href="http://go.microsoft.com/fwlink/p/?linkid=285379">http://go.microsoft.com/fwlink/p/?LinkId=285379</A>.


