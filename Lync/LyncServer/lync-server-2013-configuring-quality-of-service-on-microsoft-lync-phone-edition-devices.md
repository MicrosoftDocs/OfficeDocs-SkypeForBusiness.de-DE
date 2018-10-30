---
title: Konfigurieren von QoS (Quality of Service) auf Geräten mit Microsoft Lync Phone Edition
TOCTitle: Konfigurieren von QoS (Quality of Service) auf Geräten mit Microsoft Lync Phone Edition
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205137(v=OCS.15)
ms:contentKeyID: 49295003
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von QoS (Quality of Service) auf Geräten mit Microsoft Lync Phone Edition

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Obwohl die Dienstqualität (Quality of Service, QoS) für Geräte wie iPhones nicht standardmäßig aktiviert ist, wird QoS standardmäßig für Geräte aktiviert, auf denen Lync Phone Edition ausgeführt wird. (Diese Geräte werden im Allgemeinen als UC- oder Unified Communication-Telefone bezeichnet.) Um dies zu überprüfen, führen Sie in der Lync Server-Verwaltungsshell den folgenden Windows PowerShell-Befehl aus:

    Get-CsUCPhoneConfiguration

Wenn Sie an Ihren UC-Telefonkonfigurationseinstellungen keine Änderungen vorgenommen haben, werden die folgenden Informationen zurückgegeben:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Für die Dienstqualität ist nur eine dieser Eigenschaften von Interesse: "VoiceDiffServTag". Die Eigenschaft "VoiceDiffServTag" stellt den DSCP-Wert dar, der dem von einem Lync Phone Edition-Gerät stammenden Sprachdatenverkehr zugeordnet ist.


> [!NOTE]
> Der Parameter "Voice8021p" wird in Lync Server 2013 nicht mehr unterstützt. Obwohl er für die Abwärtskompatibiltät mit Microsoft Lync Server 2010 weiterhin gültig ist, hat er keine Auswirkung auf Geräte, die mit Lync Server 2013 verwendet werden.



In den meisten Netzwerken sollten durch die Markierung von Lync Phone Edition-Paketen mit dem Wert 40 für "VoiceDiffServTag" keine Probleme verursacht werden. Der Wert 40 ist jedoch nicht der normalerweise für Audiodatenverkehr verwendete Wert; stattdessen wird der Audiodatenverkehr fast immer mit dem DSCP-Code 46 markiert. Für die Beibehaltung der Konsistenz in Ihrem Netzwerk sollten Sie die Eigenschaft "VoiceDiffServTag" Ihrer UC-Telefone in den Wert 46 ändern.

Dazu können Sie Windows PowerShell oder Lync Server-Systemsteuerung verwenden. Wenn Sie den Wert für "VoiceDiffServTag" mithilfe von Windows PowerShell ändern möchten, führen Sie in der Lync Server-Verwaltungsshell den folgenden Befehl aus:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Mithilfe des vorherigen Befehls wird die globale Sammlung der UC-Telefonkonfigurationseinstellungen geändert. Beachten Sie jedoch, dass die UC-Telefoneinstellungen auch der Standortebene zugeordnet werden können. Wenn Sie die UC-Telefonkonfigurationseinstellungen auf Standortebene ändern möchten, müssen Sie die Standortidentität angeben. Beispiel:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Sie können auch die folgenden Befehle verwenden, um alle UC-Telefonkonfigurationseinstellungen gleichzeitig zu ändern:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Wenn Sie diese Änderung lieber mit Lync Server-Systemsteuerung vornehmen möchten, starten Sie die Systemsteuerung, und wenden Sie dann das folgende Verfahren an:

1.  Klicken Sie auf **Clients** und anschließend auf **Gerätekonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** auf die Sammlung von Einstellungen, die Sie ändern möchten (z. B. **Global**).

3.  Legen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** den Wert des Felds **VoIP-Dienstqualität (QoS)** auf **46** fest, und klicken Sie dann auf **Commit**.

Wenn Sie mehrere Sammlungen haben, müssen Sie diesen Prozess für alle Sammlungen mit UC-Telefoneinstellungen wiederholen. In Lync Server-Systemsteuerung ist die gleichzeitige Änderung mehrerer Einstellungssammlungen unzulässig.

Wenn Sie in Ihrer Organisation über Geräte verfügen, die nicht auf dem Windows-Betriebssystem basieren (beispielsweise iPhones), sind diese Geräte von der Änderung der Einstellung VoiceDiffServTag nicht betroffen. Wenn Sie auf diesen Geräten die DSCP-Werte ändern möchten, müssen Sie im jeweiligen Verwaltungshandbuch für die einzelnen Geräteteypen nachschlagen.

