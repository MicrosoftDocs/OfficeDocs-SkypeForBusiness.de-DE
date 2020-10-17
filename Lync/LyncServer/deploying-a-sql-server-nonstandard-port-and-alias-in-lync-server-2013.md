---
title: Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013
description: Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551231"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="b4a6d-103">Bereitstellen eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a6d-103">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a6d-104">_**Letztes Änderungsstand des Themas:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="b4a6d-104">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="b4a6d-105">Microsoft lync Server 2013 unterstützt die Verwendung eines nicht standardmäßigen Ports und Alias in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-105">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="b4a6d-106">Durch die Verwendung eines SQL Server nicht standardmäßigen Ports und eines Alias wird die Sicherheit erhöht und eine flexiblere Umgebung für die lync-Bereitstellung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-106">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="b4a6d-107">Diese Schritte sind nur ein einzelner Schritt bei der ordnungsgemäßen Sicherung ihrer lync Server 2013 Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-107">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="b4a6d-108">Es sollten zusätzliche Schritte unternommen werden, um die Angriffsfläche einer lync Server 2013 Implementierung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-108">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="b4a6d-109">Im folgenden Artikel werden die erforderlichen Schritte zum Einrichten eines SQL Server nicht standardmäßigen Ports und Alias in lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-109">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="b4a6d-110">Bereitstellen eines SQL Server nicht Standard mäßigen Ports und Alias in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a6d-110">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="b4a6d-111">Lync Server 2013 Topologie-Generator unterstützt die Verwendung eines SQL Server Alias als vollqualifizierter Domänen Name (Fully Qualified Domain Name, FQDN) anstelle des tatsächlichen SQL Server FQDN beim Konfigurieren von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-111">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="b4a6d-112">Dadurch kann der tatsächliche SQL Server FQDN vor böswilligen Angreifern ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-112">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="b4a6d-113">Darüber hinaus wird durch die Verwendung eines nicht standardmäßigen Ports der tatsächliche Port von einem Angreifer verdeckt, der versucht, die Datenbank am Standard Port 1433 anzugreifen, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-113">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="b4a6d-114">![Ein Hacker kennt die angegriffene Portnummer nicht.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Ein Hacker kennt die angegriffene Portnummer nicht.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-114">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="b4a6d-115">Um bei der Bestimmung des Ports, der für die Kommunikation mit SQL Server verwendet wird, erfolgreich zu sein, müsste der Angreifer alle Ports überprüfen, um die Portinformationen zu erhalten. lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a6d-115">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="b4a6d-116">Eine Portüberprüfung durch einen Angreifer erhöht die Wahrscheinlichkeit, dass die Sicherheit die Anweisung erkennen und beenden kann.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-116">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="b4a6d-117">Zusätzlich zum Hinzufügen erhöhter Sicherheit mit einem nicht standardmäßigen Port können Sie auch einen SQL Server-Alias verwenden, um Flexibilität für die Bereitstellung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-117">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="b4a6d-118">Dies ist hilfreich, um Konfigurationsänderungen in Situationen zu reduzieren, in denen eine SQL Server Namensänderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-118">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a6d-119">SQL Server bietet zwei Fehlertoleranz Methoden (Failover-Clusterunterstützung und-Spiegelung).</span><span class="sxs-lookup"><span data-stu-id="b4a6d-119">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="b4a6d-120">Beide SQL Server-Fehlertoleranz Methoden werden mit einem SQL Server nicht standardmäßigen Port und Alias mit lync Server 2013 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-120">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="b4a6d-121">Wenn sich das vom Pool verwendete SQL Server-Back-End in einer gespiegelten Konfiguration befindet, sollte der SQL-Browserdienst auf den SQL Server-Back-End-Servern für Front-End-Server ausgeführt werden, um eine Verbindung mit der gespiegelten Datenbank herzustellen, wenn die Datenbanken auf den gespiegelten SQL Server gescheitert sind.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-121">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="b4a6d-122">Beim Konfigurieren SQL Serverer Datenbankkonnektivität innerhalb des Topologie-Generators oder bei Verwendung des Install-CsDatabase-Cmdlets ist es nicht möglich, explizit eine SQL Server nicht standardmäßige Portnummer zu definieren und diese einer SQL-Instanz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-122">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="b4a6d-123">Zum Festlegen eines nicht standardmäßigen Ports müssen Sie SQL Server-und Windows Server-Dienstprogramme verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-123">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="b4a6d-124">Um einen SQL Server nicht standardmäßigen Port und Alias für die Verwendung mit lync Server 2013 einzurichten, müssen Sie drei primäre Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-124">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="b4a6d-125">Die folgenden Schritte sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b4a6d-125">These steps are:</span></span>

  - <span data-ttu-id="b4a6d-126">Vergewissern Sie sich, dass lync Server 2013 die neuesten Updates angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-126">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="b4a6d-127">Richten Sie den SQL Server nicht Standard mäßigen Port und Alias ein.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-127">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="b4a6d-128">Konfigurieren Sie lync Server 2013 mit dem SQL Server-Alias mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-128">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="b4a6d-129">Veröffentlichen Sie die Topologie, und überprüfen Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-129">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="b4a6d-130">Vergewissern Sie sich, dass lync Server 2013 die neuesten Updates angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-130">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="b4a6d-131">Es ist wichtig, lync Server 2013 auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-131">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="b4a6d-132">Informationen zum Überprüfen der neuesten Aktualisierungen und Informationen zum Anwenden dieser Updates finden Sie unter [Updates für lync Server 2013](https://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="b4a6d-132">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="b4a6d-133">Einrichten des SQL Server nicht Standard mäßigen Ports und Alias</span><span class="sxs-lookup"><span data-stu-id="b4a6d-133">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="b4a6d-134">Die SQL Server nicht standardmäßigen Port und Alias müssen auf der Datenbankinstanz eingerichtet werden, bevor Sie von lync Server 2013 Topologie-Generator referenziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-134">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="b4a6d-135">Um einen SQL Server nicht standardmäßigen Port und Alias einzurichten, müssen Sie drei primäre Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-135">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="b4a6d-136">Diese Schritte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b4a6d-136">These steps are as follows:</span></span>

  - <span data-ttu-id="b4a6d-137">Ändern Sie die Standardwerte für TCP/IP-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-137">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="b4a6d-138">Erstellen und konfigurieren Sie einen SQL Server-Alias.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-138">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="b4a6d-139">Erstellen Sie einen CNAME-Ressourceneintrag (Domain Name System (DNS) Canonical Name).</span><span class="sxs-lookup"><span data-stu-id="b4a6d-139">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="b4a6d-140">**Ändern der Standardwerte für TCP/IP-Protokolle**</span><span class="sxs-lookup"><span data-stu-id="b4a6d-140">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="b4a6d-141">Wählen Sie **Start**aus, und wählen Sie **SQL Server Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-141">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-142">![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-142">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="b4a6d-143">Wählen Sie im Navigationsbereich aus, um die **SQL Server Instanz**zu erweitern, wählen Sie aus, um **SQL Server Netzwerkkonfiguration**zu erweitern, und wählen Sie \*\*Protokolle für aus \<instance name\> \*\*, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-143">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-144">![Navigieren zu TCP/IP-Eigenschaften](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigieren zu TCP/IP-Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-144">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="b4a6d-145">Klicken Sie im rechten Bereich mit der rechten Maustaste auf **TCP/IP**, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-145">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="b4a6d-146">Das Dialogfeld TCP/IP-Eigenschaften wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-146">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="b4a6d-147">Klicken Sie auf die Registerkarte **IP-Adressen** . Auf der Registerkarte IP-Adressen werden alle aktiven IP-Adressen auf dem Server angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-147">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="b4a6d-148">Diese befinden sich im Format IP1, IP2, bis IPAll, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-148">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-149">![Öffnen Sie die TCP/IP-Eigenschaften.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Öffnen Sie die TCP/IP-Eigenschaften.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-149">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="b4a6d-150">Deaktivieren Sie das Feld **dynamische TCP-Ports** für alle IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-150">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="b4a6d-151">Wenn das Feld ein Nullzeichen enthält, bedeutet dies, dass SQL Server dynamische Ports überwacht.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-151">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="b4a6d-152">Stellen Sie sicher, dass diese Felder deaktiviert sind und keine NULL enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-152">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="b4a6d-153">Stellen Sie für die IP-Adresse, mit der lync Server eine Verbindung mit der Datenbank herstellen wird, sicher, dass **Enabled** auf **Ja**festgelegt ist, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-153">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-154">![Legen Sie für die richtige IP-Adresse aktiviert als Ja fest.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Legen Sie für die richtige IP-Adresse aktiviert als Ja fest.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-154">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="b4a6d-155">Geben Sie im Abschnitt **IPAll** im unteren Bereich des Dialogfelds den gewünschten Port in das Feld **TCP-Port** ein, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-155">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="b4a6d-156">In diesem Beispiel verwenden wir Port 50062, aber Sie können einen beliebigen Port zwischen 49152 und 65535 verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-156">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="b4a6d-157">Dabei handelt es sich um die Ports, die dynamischer und privater Nutzung zugewiesen sind, und dadurch wird sichergestellt, dass Sie nicht mit anderen Ports in der lync Server 2013-Bereitstellung in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-157">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="b4a6d-158">![Port im Abschnitt IPAll festlegen.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Port im Abschnitt IPAll festlegen.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-158">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="b4a6d-159">Wählen Sie **OK** aus, um das Dialogfeld TCP/IP-Eigenschaften zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-159">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="b4a6d-160">Starten Sie die SQL Server-Instanz neu, indem Sie im linken Bereich von SQL Server Configuration Manager **SQL Server Dienste** auswählen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-160">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="b4a6d-161">Klicken Sie dann im rechten Bereich mit der rechten Maustaste auf \*\* \<instance name\> SQL Server\*\* , und wählen Sie **neu starten**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-161">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-162">![Setzen Sie beispielsweise den SQL Server Dienst zurück.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Setzen Sie beispielsweise den SQL Server Dienst zurück.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-162">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b4a6d-163">Stellen Sie sicher, dass Sie die Firewalleinstellungen so aktualisieren, dass Sie dem neuen SQL Server-Port entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-163">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="b4a6d-164">**Erstellen und Konfigurieren eines SQL Server Alias**</span><span class="sxs-lookup"><span data-stu-id="b4a6d-164">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="b4a6d-165">Wählen Sie **Start**aus, und wählen Sie **SQL Server Konfigurations-Manager**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-165">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-166">![Das SQL Server Management Studio-Symbol](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Das SQL Server Management Studio-Symbol")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-166">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="b4a6d-167">Wählen Sie im linken Bereich **SQL Server Instanz**erweitern aus, und wählen Sie aus, um die **SQL Native Client- \<version\> Konfiguration**zu erweitern, und wählen Sie dann **Aliase**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-167">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-168">![Aliase in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliase in SQL Server Configuration Manager.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-168">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="b4a6d-169">Klicken Sie mit der rechten Maustaste auf **Aliase**, und wählen Sie **Neuer Alias**aus.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-169">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="b4a6d-170">Geben Sie den **Alias Namen**, die **Port Nummer**, das **Protokoll**und den **Server**ein, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-170">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-171">![Erstellen eines neuen Alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Erstellen eines neuen Alias")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-171">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="b4a6d-172">Stellen Sie sicher, dass Sie denselben nicht standardmäßigen Port eingeben, den Sie im vorherigen Schritt verwendet haben, da dies der Port ist, auf dem SQL Server überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-172">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="b4a6d-173">Wenn ein konfigurierter Alias eine Verbindung mit dem falschen SQL Server FQDN oder einer Instanz herstellt, deaktivieren Sie das zugehörige Netzwerkprotokoll, und aktivieren Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-173">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="b4a6d-174">Dadurch werden alle zwischengespeicherten Verbindungsinformationen gelöscht, und der Client kann eine ordnungsgemäße Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-174">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="b4a6d-175">**Erstellen eines DNS-CNAME-Ressourceneintrags**</span><span class="sxs-lookup"><span data-stu-id="b4a6d-175">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="b4a6d-176">Melden Sie sich beim Computer an, der DNS verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-176">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="b4a6d-177">Wählen Sie **Start**aus, und wählen Sie **Server-Manager**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-177">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-178">![Öffnen des Server-Managers](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Öffnen des Server-Managers")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-178">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="b4a6d-179">Wählen Sie die Dropdownliste **Tools** aus, und wählen Sie **DNS**aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-179">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-180">![Öffnen von DNS im Server-Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Öffnen von DNS im Server-Manager.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-180">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="b4a6d-181">Erweitern Sie im linken Bereich den Knoten Servername, erweitern Sie den Knoten Forward-Nachschlage Zonen, und wählen Sie die entsprechende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-181">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="b4a6d-182">Klicken Sie mit der rechten Maustaste auf die Domäne, und wählen Sie **New Alias (CNAME)...** aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-182">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-183">![Auswählen der Option zum Erstellen eines neuen Alias-CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Auswählen der Option zum Erstellen eines neuen Alias-CNAME")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-183">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="b4a6d-184">Geben Sie den **Alias Namen** und den **FQDN für SQL Server**ein, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-184">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-185">![Füllen Sie das Dialogfeld Neuer Alias-CNAME aus.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Füllen Sie das Dialogfeld Neuer Alias-CNAME aus.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-185">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="b4a6d-186">Wählen Sie **OK** aus, um den CNAME zu speichern und im DNS-Manager anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-186">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="b4a6d-187">Überprüfen der Datenbankkonnektivität</span><span class="sxs-lookup"><span data-stu-id="b4a6d-187">Validate Database Connectivity</span></span>

<span data-ttu-id="b4a6d-188">Es gibt viele verschiedene Möglichkeiten, um sicherzustellen, dass es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-188">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="b4a6d-189">Sie möchten sicherstellen, dass die SQL Server Datenbank den angegebenen Port mithilfe des Alias überwacht.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-189">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="b4a6d-190">Eine Schnellüberprüfung kann mit den Befehlen **netstat** und **Telnet** abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-190">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a6d-191">Der Telnet-Client ist ein Feature, das mit Windows Server ausgeliefert wird, aber installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-191">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="b4a6d-192">Ein Windows Server-Feature kann installiert werden, indem Sie Server-Manager öffnen und im Menü verwalten die Option Rollen und Features hinzufügen auswählen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-192">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="b4a6d-193">**Verwenden von netstat und Telnet zum Überprüfen der Datenbankkonnektivität**</span><span class="sxs-lookup"><span data-stu-id="b4a6d-193">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="b4a6d-194">Wählen Sie **Start**, und geben Sie **cmd** ein, um eine Eingabeaufforderung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-194">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="b4a6d-195">Geben Sie **netstat-a-f ein**, und bestätigen Sie, dass SQL Server mit dem korrekten Port läuft, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-195">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b4a6d-196">![Verwenden von netstat zum Überprüfen des Ports.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Verwenden von netstat zum Überprüfen des Ports.")</span><span class="sxs-lookup"><span data-stu-id="b4a6d-196">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="b4a6d-197">Geben **Sie \<alias name\> \<port \#\> Telnet** ein, um die Verbindung mit der SQL Server Instanz zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-197">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="b4a6d-198">Wenn die Verbindung erfolgreich hergestellt wurde, stellt Telnet eine Verbindung her, und es sollte kein Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-198">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="b4a6d-199">Dies zeigt, dass die SQL Server Instanz den korrekten Port mit dem korrekten Alias überwacht.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-199">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="b4a6d-200">Wenn beim Herstellen einer Verbindung mit der SQL Server Datenbank ein Problem auftritt, zeigt Telnet einen Fehler an, bei dem die Verbindung nicht hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-200">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="b4a6d-201">Nachdem Sie nun die Datenbankkonnektivität auf dem Datenbankserver überprüft haben, können Sie dasselbe von lync Server (über das Netzwerk) durchführen und sicherstellen, dass keine Firewalls den Zugriff auf dem Weg blockieren.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-201">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="b4a6d-202">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="b4a6d-202">Conclusion</span></span>

<span data-ttu-id="b4a6d-203">Nachdem der SQL Server-Alias konfiguriert wurde, können Sie ihn verwenden, um eine lync Server 2013 Topologie im Topologie-Generator-Tool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4a6d-203">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="b4a6d-204">Weitere Informationen zu Topologien finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="b4a6d-204">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4a6d-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4a6d-205">See Also</span></span>


<span data-ttu-id="b4a6d-206">[Microsoft lync Server 2013](microsoft-lync-server-2013.md)  
 [Planen der Sicherheit in lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="b4a6d-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="b4a6d-207">Definieren und Konfigurieren der Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a6d-207">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="b4a6d-208">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a6d-208">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

