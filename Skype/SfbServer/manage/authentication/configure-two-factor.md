---
title: Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Zusammenfassung: Konfigurieren einer zweistufigen Authentifizierung in Skype für Business Server.'
ms.openlocfilehash: cc73997fffcae3ef7d63e32898173fe68ecb9447
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "25694576"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="29ea7-103">Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="29ea7-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="29ea7-104">**Zusammenfassung:** Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="29ea7-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="29ea7-105">In den folgenden Abschnitten werden die erforderlichen Schritte beschrieben, um für eine Bereitstellung zweistufige Authentifizierungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="29ea7-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="29ea7-106">Weitere Informationen zur zweistufigen Authentifizierung finden Sie unter [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="29ea7-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="29ea7-107">Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="29ea7-108">In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="29ea7-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="29ea7-109">Informationen zum Installieren einer Stammzertifizierungsstelle im Unternehmen finden Sie in [Installieren einer Stammzertifizierungsstelle](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="29ea7-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="29ea7-110">Melden Sie sich beim CA-Computer des Unternehmens mit dem Konto eines Domänenadministrators an.</span><span class="sxs-lookup"><span data-stu-id="29ea7-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="29ea7-111">Starten Sie den System-Manager und überprüfen Sie, ob die Zertifizierungsstellen-Webregistrierungsrolle installiert ist.</span><span class="sxs-lookup"><span data-stu-id="29ea7-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="29ea7-112">Öffnen Sie im Menü **Verwaltungstools** die Verwaltungskonsole **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="29ea7-113">Erweitern Sie im Navigationsbereich den Knoten **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="29ea7-114">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **Neu** und anschließend **Auszustellende Zertifikatvorlage** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="29ea7-115">Wählen Sie **Enrollment Agent**, **SmartCard-Benutzer** und **SmartCard-Anmeldung** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="29ea7-116">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-116">Click **OK**.</span></span>

8. <span data-ttu-id="29ea7-117">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="29ea7-118">Wählen Sie **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-118">Select **Manage**.</span></span>

10. <span data-ttu-id="29ea7-119">Öffnen Sie die Eigenschaften der Vorlage „SmartCard-Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="29ea7-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="29ea7-120">Klicken Sie auf die Registerkarte **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="29ea7-121">Ändern Sie die Berechtigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="29ea7-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="29ea7-122">Fügen Sie einzelne AD-Konten mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ hinzu, oder</span><span class="sxs-lookup"><span data-stu-id="29ea7-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="29ea7-123">Fügen Sie eine Sicherheitsgruppe hinzu, die SmartCard-Benutzer mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ enthält, hinzu, oder</span><span class="sxs-lookup"><span data-stu-id="29ea7-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="29ea7-124">Fügen Sie die Gruppe „Domänenbenutzer“ mit den Berechtigungen „Lesen/Registrieren (Zulassen“) hinzu</span><span class="sxs-lookup"><span data-stu-id="29ea7-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="29ea7-125">Konfigurieren von Windows 8 für virtuelle Smartcards</span><span class="sxs-lookup"><span data-stu-id="29ea7-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="29ea7-126">Ein zu berücksichtigender Faktor bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie sind die Kosten der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="29ea7-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="29ea7-127">Windows 8 bietet eine Reihe von neuen Sicherheitsfunktionen, und eine der interessantesten neuen Features Unterstützung für virtuelle Smart Karten ist.</span><span class="sxs-lookup"><span data-stu-id="29ea7-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="29ea7-128">Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="29ea7-129">Weitere Informationen hierzu finden Sie unter [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="29ea7-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="29ea7-130">So konfigurieren Sie Windows 8 für virtuelle Smartcards</span><span class="sxs-lookup"><span data-stu-id="29ea7-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="29ea7-131">Melden Sie sich an den Windows 8-Computer mit den Anmeldeinformationen des einen Skype für Business-aktivierten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29ea7-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="29ea7-132">Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="29ea7-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="29ea7-133">Wählen Sie eine **Suchoption** aus, und suchen Sie anschließend nach Aufforderung ForCommand.</span><span class="sxs-lookup"><span data-stu-id="29ea7-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="29ea7-134">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und wählen Sie dann **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="29ea7-135">Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="29ea7-136">Vergewissern Sie sich in der TPM-Verwaltungskonsole, dass die TPM-Spezifikationsversion mindestens 1.2 ist.</span><span class="sxs-lookup"><span data-stu-id="29ea7-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="29ea7-137">Wird ein Dialogfeld angezeigt, in dem gemeldet wird, dass kein kompatibles Trusted Platform Module (TPM) gefunden wurde, sollten Sie sich vergewissern, dass der Computer ein kompatibles TPM hat und dass dieses im System-BIOS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29ea7-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="29ea7-138">Schließen Sie die TPM-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="29ea7-138">Close the TPM management console</span></span>

8. <span data-ttu-id="29ea7-139">Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard, indem Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="29ea7-140">Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie „/pin prompt“ anstelle von „/pin default“.</span><span class="sxs-lookup"><span data-stu-id="29ea7-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="29ea7-141">Öffnen Sie über die Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="29ea7-142">Wählen Sie in der Computerverwaltungskonsole den Eintrag **Geräte-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="29ea7-143">Erweitern Sie **Smartcard-Leser**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="29ea7-144">Vergewissern Sie sich, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29ea7-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="29ea7-145">Registrieren von Benutzern für die SmartCard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="29ea7-p104">Allgemein bestehen zwei Verfahren für das Registrieren von Benutzern für die SmartCard-Authentifizierung. Das einfachere Verfahren sieht die direkte Registrierung der Benutzer für die SmartCard-Authentifizierung mithilfe der Webregistrierung vor, während bei der komplexeren Methode ein Enrollment Agent verwendet wird. Dieses Thema legt den Schwerpunkt auf die Selbstregistrierung der Benutzer für SmartCard-Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="29ea7-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="29ea7-149">Weitere Informationen zur Registrierung im Auftrag von Benutzern als Enrollment Agent finden Sie in [Registrieren von Zertifikaten im Auftrag von anderen Benutzern](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="29ea7-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="29ea7-150">So registrieren Sie Benutzer für die SmartCard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="29ea7-151">Melden Sie sich an der Windows 8-Arbeitsstation mit den Anmeldeinformationen des einen Skype für Business-aktivierten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29ea7-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="29ea7-152">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="29ea7-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="29ea7-153">Wechseln Sie zur Seite **Certificate Authority Web-Registrierung** (z. B. https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="29ea7-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="29ea7-154">Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="29ea7-155">Wählen Sie auf der Seite **Willkommen** die Option **Zertifikat anfordern** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="29ea7-156">Wählen Sie im nächsten Schritt **Erweiterte Anforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="29ea7-157">Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="29ea7-158">Wählen Sie im Abschnitt **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus und füllen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten aus:</span><span class="sxs-lookup"><span data-stu-id="29ea7-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="29ea7-159">**Schlüsseloptionen** – bestätigen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="29ea7-160">Aktivieren Sie das Optionsfeld **Neuen Schlüsselsatz erstellen**</span><span class="sxs-lookup"><span data-stu-id="29ea7-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="29ea7-161">Wählen Sie für **CSP** die Option **Microsoft Basis-SmartCard-Krypto-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="29ea7-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="29ea7-162">Wählen Sie für **Schlüsselverwendung** den Wert **Exchange** aus (dies ist die einzige verfügbare Option).</span><span class="sxs-lookup"><span data-stu-id="29ea7-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="29ea7-163">Geben Sie unter **Schlüsselgröße** den Wert 2048 ein</span><span class="sxs-lookup"><span data-stu-id="29ea7-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="29ea7-164">Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="29ea7-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="29ea7-165">Lassen Sie die anderen Felder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="29ea7-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="29ea7-166">Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="29ea7-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="29ea7-167">Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="29ea7-168">Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="29ea7-169">Für **Anzeigename** EnterSmardcard Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="29ea7-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="29ea7-170">Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="29ea7-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="29ea7-171">Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="29ea7-172">Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="29ea7-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="29ea7-173">Der Standardwert für virtuelle Smartcard PIN ist "12345678".</span><span class="sxs-lookup"><span data-stu-id="29ea7-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="29ea7-174">Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="29ea7-175">Schlägt der zertifikatanforderung den Fehler "in Webbrowser unterstützt nicht die Generierung von zertifikatanforderungen", gibt es drei verschiedene Arten zur Behebung des Problems:</span><span class="sxs-lookup"><span data-stu-id="29ea7-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="29ea7-176">Konfigurieren von Active Directory-Partnerverbunddiensten (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="29ea7-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="29ea7-177">Im folgenden Abschnitt wird beschrieben, wie Active Directory-Partnerverbunddienste (AD FS 2.0) konfiguriert werden muss, damit die mehrstufige Authentifizierung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="29ea7-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="29ea7-178">Informationen, wie AD FS 2.0 installiert wird, finden Sie unter [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="29ea7-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="29ea7-179">Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Partnerverbunddienste-Rolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="29ea7-180">Laden Sie stattdessen das Paket [Active Directory Federation Services 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375) herunter und installieren Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="29ea7-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="29ea7-181">So konfigurieren Sie AD FS für die zweistufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="29ea7-182">Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="29ea7-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="29ea7-183">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ea7-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="29ea7-184">Führen Sie aus der Windows PowerShell-Befehlszeile den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="29ea7-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="29ea7-185">Richten Sie eine Partnerschaft mit jedem Server ein, der für die passive Authentifizierung aktiviert werden soll, indem Sie den folgenden Befehl ausführen, und ersetzen Sie den für Ihre Bereitstellung spezifischen Servernamen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="29ea7-186">Starten Sie aus dem Menü „Verwaltung“ die AD FS 2.0-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="29ea7-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="29ea7-187">Erweitern Sie **Vertrauensstellungen** > **Relying Party Trusts**.</span><span class="sxs-lookup"><span data-stu-id="29ea7-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="29ea7-188">Stellen Sie sicher, dass eine neue Vertrauensstellung für Ihre Skype für Business Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29ea7-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="29ea7-189">Erstellen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="29ea7-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="29ea7-190">Erstellen Sie eine Ausstellungstransformationsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="29ea7-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="29ea7-191">Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf Ihre Vertrauensstellung der vertrauenden Seite und wählen Sie **Anspruchsregeln bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="29ea7-192">Wählen Sie die Registerkarte **Ausstellungsautorisierungsregeln** aus und vergewissern Sie sich, dass die neue Autorisierungsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29ea7-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="29ea7-193">Wählen Sie die Registerkarte **Ausstellungstransformationsregeln** aus und vergewissern Sie sich, dass die neue Transformationsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29ea7-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="29ea7-194">Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="29ea7-195">Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 Authentifizierung über Smartcards unterstützen kann:</span><span class="sxs-lookup"><span data-stu-id="29ea7-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="29ea7-196">Formularbasierte Authentifizierung (FBA)</span><span class="sxs-lookup"><span data-stu-id="29ea7-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="29ea7-197">Transport Layer Security-Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="29ea7-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="29ea7-198">Wenn Sie formularbasierte Authentifizierung verwenden, können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit der Kombination aus Benutzername und Kennwort oder mit Smartcard und PIN zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="29ea7-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="29ea7-199">Im vorliegenden Thema wird beschrieben, wie Transport Layer Security-Clientauthentifizierung mit AD FS 2.0 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="29ea7-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="29ea7-200">Weitere Informationen zu den Authentifizierungstypen von AD FS 2.0 finden Sie unter [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="29ea7-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="29ea7-201">So konfigurieren Sie AD FS 2.0, sodass Clientauthentifizierung unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="29ea7-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="29ea7-202">Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="29ea7-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="29ea7-203">Starten Sie Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="29ea7-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="29ea7-204">Navigieren Sie zu „C:\inetpub\adfs\ls“</span><span class="sxs-lookup"><span data-stu-id="29ea7-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="29ea7-205">Erstellen Sie eine Sicherungskopie von der vorhandenen Datei „web.config“.</span><span class="sxs-lookup"><span data-stu-id="29ea7-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="29ea7-206">Öffnen Sie die vorhandene Datei „web.config“ im Editor.</span><span class="sxs-lookup"><span data-stu-id="29ea7-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="29ea7-207">Wählen Sie in der Menüleiste das Menü **Bearbeiten** und anschließend **Suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="29ea7-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="29ea7-208">Suchen Sie nach \<LocalAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="29ea7-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="29ea7-209">Es werden vier Authentifizierungstypen aufgelistet (je ein Typ pro Zeile).</span><span class="sxs-lookup"><span data-stu-id="29ea7-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="29ea7-210">Verschieben Sie die Zeile, die den Authentifizierungstyp „TLSClient“ enthält, an den Anfang der Liste im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="29ea7-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="29ea7-211">Speichern Sie die Datei „web.config“ und beenden Sie den Editor.</span><span class="sxs-lookup"><span data-stu-id="29ea7-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="29ea7-212">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="29ea7-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="29ea7-213">Starten Sie IIS neu, indem Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="29ea7-214">Konfigurieren der passiven Authentifizierung für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="29ea7-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="29ea7-215">Im folgende Abschnitt wird beschrieben, wie Skype für Business Server zur Unterstützung der passiven Authentifizierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="29ea7-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="29ea7-216">Nach der Aktivierung werden von einer physischen oder virtuellen Smartcard und eine gültige PIN zum Melden Sie sich über die Skype für Business Client erforderlich Benutzer, die für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29ea7-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="29ea7-p109">Kunden wird dringend empfohlen, die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene zu aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf der globalen Ebene aktiviert wird, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem unterstützten Desktopclient anmelden.</span><span class="sxs-lookup"><span data-stu-id="29ea7-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="29ea7-219">Webdienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="29ea7-219">Web Service Configuration</span></span>

<span data-ttu-id="29ea7-220">In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29ea7-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="29ea7-221">So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="29ea7-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="29ea7-222">Melden Sie sich bei Ihrer Skype für Business Server-Front-End-Server mit einer Skype für Business-Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="29ea7-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="29ea7-223">Starten Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="29ea7-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="29ea7-224">Erstellen Sie über die Skype für Business Server-Verwaltungsshell Command-Line eine neue Konfiguration für den Webdienst für jeden Director, Enterprise-Pool und Standard Edition-Server, die für passiven Authentifizierung mithilfe des folgenden Befehls aktiviert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="29ea7-p110">Der Wert für den vollqualifizierten Domänennamen in „WsFedPassiveMetadataUri“ ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf **Dienst** klicken und dann **Eigenschaften des Verbunddiensts bearbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="29ea7-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="29ea7-227">Überprüfen Sie, ob die Werte von „UseWsFedPassiveAuth“ und „WsFedPassiveMetadataUri“ richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="29ea7-228">Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar.</span><span class="sxs-lookup"><span data-stu-id="29ea7-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="29ea7-229">Für alle Directors, Enterprise-Pools und Standard Edition-Servern, die für passiven Authentifizierung aktiviert werden sollen, müssen alle Authentifizierungstypen in Skype für Webdienste Business deaktiviert werden durch das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="29ea7-230">Überprüfen Sie, ob alle anderen Authentifizierungsarten erfolgreich deaktiviert wurden, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="29ea7-231">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="29ea7-231">Proxy Configuration</span></span>

<span data-ttu-id="29ea7-232">Wenn Zertifikatauthentifizierung für Business-Webdienste für Skype deaktiviert ist, wird die Skype für Business-Client eine weniger bevorzugten Authentifizierungstyp wie Kerberos oder NTLM verwenden, um auf den Registrierungsdienst authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="29ea7-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="29ea7-233">Die Zertifikatauthentifizierung ist nach wie vor erforderlich, um dem Client das Abrufen eines Webtickets zu ermöglichen, jedoch müssen Kerberos und NTLM für den Registrierungsstellendienst deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="29ea7-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="29ea7-234">In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29ea7-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="29ea7-235">So erstellen Sie eine benutzerdefinierte Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="29ea7-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="29ea7-236">Erstellen Sie aus der Skype für Business Server-Verwaltungsshell Command-Line eine neue Proxykonfiguration für jede Skype für Edge-Serverpool Business, Enterprise-Pool und Standard Edition-Server, die für passiven Authentifizierung durch Ausführen des folgenden aktiviert werden sollen Befehle:</span><span class="sxs-lookup"><span data-stu-id="29ea7-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="29ea7-237">Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="29ea7-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="29ea7-238">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29ea7-238">See also</span></span>

[<span data-ttu-id="29ea7-239">Verwalten der zweistufigen Authentifizierung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="29ea7-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="29ea7-240">Verwenden Sie zweistufige Authentifizierung mit Skype für Business Client- und Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="29ea7-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)