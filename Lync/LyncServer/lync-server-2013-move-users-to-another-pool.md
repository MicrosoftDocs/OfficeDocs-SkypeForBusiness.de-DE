---
title: Verschieben von Benutzern in einen anderen Pool
TOCTitle: Verschieben von Benutzern in einen anderen Pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182600(v=OCS.15)
ms:contentKeyID: 49295745
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Benutzern in einen anderen Pool

 

_**Letztes Änderungsdatum des Themas:** 2013-03-11_

Sie können die Lync Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuordnen.


> [!TIP]
> Wenn Sie in einer komplexen Active Directory-Umgebung alle vorhandenen Benutzer aus einem Quellpool mit Microsoft Office Communications Server 2007 R2 oder einer früheren Version in einen Lync Server 2013-Zielpool verschieben, kann dies die Active Directory-Replikation verlangsamen. Dies können Sie vermeiden, indem Sie Benutzer aus Pools mit Microsoft Office Communications Server 2007 R2 oder einer früheren Version anhand von Suchfiltern getrennt verschieben. Oder Sie verwenden die Lync Server-Verwaltungsshell, um Benutzer mithilfe von Cmdlets zu verschieben. Darüber hinaus können Sie die Filterfunktion auch für Lync Server 2013-Benutzer verwenden.



## So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  Wählen Sie in der Tabelle einen einzelnen Benutzer oder mehrere Benutzer aus der Liste aus.

6.  Klicken Sie im Menü **Aktion** auf **Ausgewählte Benutzer in Pool verschieben**.

7.  Wählen Sie im Abschnitt **Benutzer verschieben** unter **Zielregistrierungsstellenpool** den Pool aus, in den Sie die Benutzer verschieben möchten.

8.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    

    > [!WARNING]
    > Wenn Sie <STRONG>Erzwingen</STRONG> aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z.&nbsp;B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben.



## So verschieben Sie alle Benutzer eines Servers oder Pools auf einen anderen Server oder in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.

5.  Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungsstellenpool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.

6.  Wählen Sie unter **Zielregistrierungsstellenpool** den Pool aus, in den Sie die Benutzer verschieben möchten.

7.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    

    > [!WARNING]
    > Wenn Sie <STRONG>Erzwingen</STRONG> aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z.&nbsp;B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben.



## So verschieben Sie Benutzer mithilfe eines Filters von einem Pool in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie unter **Benutzersuche** auf **Suche** und dann auf **Filter hinzufügen**.

5.  Wählen Sie in den Suchkriterien **Registrierungsstellenpool**, **Gleich** und **FQDN des aktuellen Pools** aus, und klicken Sie auf **Suchen**.

6.  Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.
    

    > [!NOTE]
    > Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, gilt die Option <STRONG>Alle Benutzer in Pool verschieben</STRONG> für die gefilterte Teilmenge der Benutzer, nicht für <STRONG><EM>alle möglichen</EM></STRONG> Benutzer.



7.  Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungsstellenpool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.

8.  Wählen Sie unter **Zielregistrierungsstellenpool** den Pool aus, in den Sie die Benutzer verschieben möchten.

9.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    

    > [!WARNING]
    > Wenn Sie <STRONG>Erzwingen</STRONG> aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z.&nbsp;B. Kontakte oder von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben.



## So verschieben Sie Benutzer mithilfe der Lync Server-Verwaltungsshell von einem Pool in einen anderen

1.  Je nachdem, wie Sie Windows PowerShell-Befehle ausführen (d. h. lokal oder remote), müssen Sie sich wie folgt als Mitglied der richtigen Lync Server 2013-Administratorrolle anmelden:
    
    1.  Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise beim Anmelden direkt auf einem Front-End-Server): Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Wenn Sie die Befehle remote auf einem anderen Computer ausführen (z. B., wenn Sie sich an Ihrem Computer anmelden und die Befehle remote auf einem Standard Edition-Front-End-Server ausführen): Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Zum Verschieben einzelner Benutzer verwenden Sie das **Move-CsUser**-Cmdlet wie folgt:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Hierbei ist der zu verschiebende Benutzer Pilar Ackerman, und dieser wird vom derzeit zugeordneten Homepool in den Pool **pool01.contoso.net** verschoben.

4.  Zum Verschieben einer großen Zahl von Benutzern verwenden Sie das **Get-CsUser**-Cmdlet mit Filtern und übergeben Sie den daraus resultierenden Benutzersatz an **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** Folgendes ergeben:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

## Siehe auch

#### Weitere Ressourcen

[Ändern der Eigenschaften von Benutzerkonten](lync-server-2013-modifying-user-account-properties.md)

