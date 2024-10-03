# code8
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fixed Layout</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            height: 100%;
            font-family: Arial, sans-serif;
            overflow-x: hidden; /* Prevents horizontal scroll on small devices */
        }

        body {
            display: block;
            background-color: #f4f4f4;
        }

        /* Image section styling */
        .image-section {
            background-color: white;
            text-align: center;
            position: relative;
            z-index: 1;
            padding-top: 20px;
            overflow: hidden; /* Prevent scrolling for the image section */
        }

        .centered-image {
            max-width: 100%;
            height: auto;
            padding-bottom: 20px;
        }

        .bottom-image {
            width: auto;
            height: auto;
            max-width: 100%;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
            display: block;
            margin-left: auto;
            margin-right: auto;
        }

        /* Ensuring bottom image is responsive */
        @media (max-width: 768px) {
            .bottom-image {
                width: 100vw;
                height: auto;
                margin: 0;
                padding: 0;
                max-height: none;
            }
        }

        .vertical-container {
            width: 90%;
            max-width: 600px;
            background-color: white;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            position: relative; /* Changed to relative */
            margin: -47.5% auto 20px;
             /* Adjust margin to overlap with image section */
            z-index: 10; /* Higher z-index so it appears above the image section */
            overflow: hidden;
        }

        /* Responsive width adjustments for vertical-container */
        /* Responsive width adjustments for vertical-container */
        @media (max-width: 768px) {
            .vertical-container {
                width: calc(100% - 40px); /* Subtracting 20px from both sides */
                margin: -4000px 20px 20px; /* 20px margin on top and bottom */
            }
        }

        @media (max-width: 480px) {
            .vertical-container {
                width: calc(100% - 40px); /* Subtracting 20px from both sides */
                margin: -760px 20px 20px; /* 20px margin on top and bottom */
            }
        }


        /* Section 1: Image only, no padding or margins */
        .section-1 {
            overflow: hidden; /* Prevents any overflow from the image */
        }

        .section-1 img {
            width: 100%; /* Set image width to 100% to fit inside the container */
            height: auto; /* Maintain aspect ratio */
            max-height: 300px; /* Set a maximum height */
            border-radius: 10px 10px 50% 50%/10px 10px 50% 50%; /* Same rounded corners */
            object-fit: cover; /* Ensures the image covers the container without stretching */
            display: block; /* Ensures block display to remove bottom space */
            transform: scaleX(1.5); /* Scale the image */
            transform-origin: center; /* Scale from the center */
        }



        /* Section 2: Content */
        .section-2 {
            padding: 20px;
            padding-top: 5px;
            background-color: #fff;
        }

        h3 {
            color: purple;
            text-align: center;
            font-size: 1rem;
        }

        .Armani {
            display: block;
            margin: 0 auto;
            padding-top: 5px;
            padding-bottom: 20px;
        }

        .firstpara {
            text-align: center;
            padding: 0 20px 5px 20px;
            font-size: 1.1rem;
        }

        .secondpara {
            text-align: center;
            font-size: 0.65rem;
        }

        /* Section 3: Clock icon and text */
        .section-3 {
            padding: 20px;
            padding-bottom: 0;
        }

        .section-3 img {
            vertical-align: middle;
            width: 24px;
            height: 24px;
        }

        .section-3 .workshop-time {
            display: inline-block;
            vertical-align: middle;
            font-size: 0.90rem;
            margin-left: 10px;
            font-weight: bold;
        }

        .section-3 .next-line {
            display: block;
            margin-top: 10px;
            font-size: 0.75rem;
            text-align: left;
        }

        /* Section 4: Form */
        .section-4 {
            padding: 20px;
            background-color: #fff;
        }

        .section-4 input[type="text"], .section-4 input[type="email"], .section-4 select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 0.90rem;
        }

        .section-4 .form-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .section-4 .form-row div {
            width: 100%;
        }

        .section-4 label {
            display: block;
            margin-bottom: 5px;
            font-size: 1rem;
        }

        .section-4 .input-container {
            position: relative; /* For positioning the star */
        }

        .section-4 .input-container::after {
            content: '*';
            color: red;
            position: absolute;
            right: 10px; /* Adjust as necessary */
            top: 12px; /* Adjust as necessary */
            font-size: 1rem;
        }

        .section-4 .confirm-btn {
            display: block;
            width: 100%;
            background-color: red;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 25px;
            font-size: 1rem;
            cursor: pointer;
            margin-top: 10px;
            font-weight: bold;
        }

        .section-5 {
            padding: 20px;
            padding-bottom: 0;
        }

        .section-5 p {
            font-size: 0.75rem;
            margin-bottom: 10px;
        }

        .section-6 {
            padding: 20px;
            position: relative;
            text-align: center;
            background-color: #fff;
        }

        .section-6 img {
            display: inline-block;
            z-index: 1;
        }

        .section-7 {
            font-size: 0.75rem;
            text-align: center;
            padding-bottom: 20px;
        }

        .section-8 {
            font-size: 0.75rem;
            text-align: center;
            padding-bottom: 100px;
            padding-left: 20px;
            padding-right: 20px;
        }

        .terms-privacy .dot {
            font-size: 1.5rem;
            font-weight: bold;
            margin: 0 10px;
            vertical-align: middle;
        }
    </style>
</head>
<body>

    <!-- Image Section -->
    <div class="image-section" style="overflow: hidden;"> <!-- Added overflow: hidden; -->
        <img src="upperlogo.png" alt="Centered Image" class="centered-image">
        <picture>
            <source media="(max-width: 768px)" srcset="image2Mobile.png">
            <source media="(min-width: 769px)" srcset="image2.png">
            <img src="image2.png" alt="Bottom Image" class="bottom-image">
        </picture>
    </div>
    <div class="vertical-container">
            <!-- Section 1: Image only, no padding or margins -->
            <div class="section-1">
                <img src="/blackimage.png" alt="Sample Image">
            </div>

            <!-- Section 2: Content -->
            <div class="section-2">
                <h3>DFS Exclusive</h3>
                <img class="Armani" src="/giorgiaArmani.png" alt="image giorgiaArmani">
                <p class="firstpara"><b>Armani Beauty Exclusive VIP Workshop (T Galleria by DFS, Macau, Shoppes at Four Seasons)</b></p>
                <p class="secondpara">Armani Beauty sincerely invites you to experience personalized Crema Nera and Armani Privé consultation (about 30 minutes). Upon completion, you can enjoy the Crema Nera Trial Kit (worth MOP 1,525)</p>
            </div>

            <!-- Section 3: Clock icon and text -->
            <div class="section-3">
                <img src="/clock.png" alt="Clock Icon">
                <span class="workshop-time">Workshop time :</span>
                <span class="next-line">February 7-8, 10-18, 23-25 2pm to 8pm</span>
            </div>

            <!-- Section 4: Form -->
            <div class="section-4">
                <p class="thirdpara" style="font-size: 0.75rem;">Please fill in the following contact details</p>
                
                <form>
                    <label for="firstname"></label>
                    <div class="input-container">
                        <input type="text" id="firstname" placeholder="Enter your first name">
                    </div>
                         
                    <label for="lastname"></label>
                    <div class="input-container">
                        <input type="text" id="lastname" placeholder="Enter your last name">
                    </div>    
                    
                    <label for="email"></label>
                    <div class="input-container"> 
                        <input type="email" id="email" placeholder="Enter your email">
                    </div>

                    <div class="form-row">
                        <div class="div1">
                            <label for="countrycode"></label>
                            <div class="input-container">
                                <select id="countrycode">
                                    <option value="">Select Code</option>
                                    <option value="+1">+1 (USA)</option>
                                    <option value="+44">+44 (UK)</option>
                                    <option value="+91">+91 (India)</option>
                                </select>
                            </div>
                        </div>
                        <div class="div2">
                            <label for="mobile"></label>
                            <div class="input-container">
                                <input type="text" id="mobile" placeholder="Mobile Number">
                            </div>
                        </div>
                    </div>

                    <div class="checkbox-container">
                        <label class="input-container" style="font-size: 0.65rem;">
                           <input type="checkbox" id="consent"> By submitting the form, I understand and agree that DFS is a global company and that my DFS CIRCLE data and order information will be processed overseas, subject to applicable laws and regulations. Also, in order to provide better service, DFS stores around the world will have the possibility to access my DFS CIRCLE account information and event registration for the purpose of event follow-up.
                        </label><br>
                        <label class="input-container" style="font-size: 0.65rem;">
                            <input type="checkbox" id="newsletter">By submitting the form, I acknowledge and agree to receive phone call/SMS/text and/or email messages via the contact information provided concerning the event registration updates or notifications, and as otherwise permitted by our privacy policy. To better understand how we process your personal data, please refer to our privacy policy.
                        </label>
                    </div>
                    <button type="submit" class="confirm-btn">Confirm</button>
                </form>
                
            </div>

            <!-- Section 5: Two paragraphs -->
            <div class="section-5">
                <p>After submission, a DFS representative will contact you for appointment details</p>
                <p>Limited availability, first-come, first served basis.</p>
            </div>

            <!-- Section 6: Centered Image -->
            <div class="section-6">
                <img src="/bottomlogo.png" alt="Centered Image">
            </div>

            <!-- Section 7: terms-privacy -->
            <div class="section-7">
                Terms &amp; Conditions <span class="dot">&bull;</span> Privacy Policy
            </div>

            <!-- Section 8: @2024 -->
            <div class="section-8">
                <p class="thirdpara">
                    © 2024 DFS Group Ltd. Enjoy duty-free shopping with DFS at our airport duty-free shops and downtown T Galleria stores worldwide
                </p>
            </div>
        </div>
    </div>
</body>
</html>
