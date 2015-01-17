# Header
Header part containers logo section, toggle switch and top-right menu
Code for Header looks like this
```html
<header class="header">
                <a target="_blank" href="index.html" class="logo">

                    <h1>JOSH</h1>
                </a>

                <nav class="navbar navbar-static-top" role="navigation">
                    <!-- Sidebar toggle button-->
                    <div>
                        <a target="_blank" href="#" class="navbar-btn sidebar-toggle" data-toggle="offcanvas" role="button">
                            <div class="responsive_nav">
                                <img src="img/nav_icon.png" width="25" height="17" alt="responsive icon" />

                            </div>
                        </a>
                    </div>

                    <div class="navbar-right">
                        <ul class="nav navbar-nav">
                            <li class="dropdown messages-menu">
                                <a target="_blank" href="#" class="dropdown-toggle" data-toggle="dropdown">
                                    <i class="livicon" data-name="message-flag" data-loop="true" data-color="#ccc" data-hovercolor="#fff" data-size="28"></i>
                                    <span class="label label-success">4</span>
                                </a>
                                <ul class="dropdown-menu">
                                    <li class="header">You have 4 messages</li>
                                    <li>
                                        <!-- inner menu: contains the actual data -->
                                        <ul class="menu">
                                            <li>
                                                <!-- start message -->
                                                <a target="_blank" href="#">
                                                    <div class="pull-left">
                                                        <img src="img/avatar3.png" class="img-circle" alt="User Image" />
                                                    </div>
                                                    <h4>
                                                        Support Team
                                                        <small><i class="fa fa-clock-o"></i> 5 mins</small>
                                                    </h4>
                                                    <p>Why not buy a new awesome theme?</p>
                                                </a>
                                            </li>
                                            <!-- end message -->
                                            <li>
                                                <a target="_blank" href="#">
                                                    <div class="pull-left">
                                                        <img src="img/avatar3.png" class="img-circle" alt="user image" />
                                                    </div>
                                                    <h4>
                                                        Admin
                                                        <small><i class="fa fa-clock-o"></i> 2 hours</small>
                                                    </h4>
                                                    <p>Why not buy a new awesome theme?</p>
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <div class="pull-left">
                                                        <img src="img/avatar3.png" class="img-circle" alt="user image" />
                                                    </div>
                                                    <h4>
                                                        Developers
                                                        <small><i class="fa fa-clock-o"></i> Today</small>
                                                    </h4>
                                                    <p>Why not buy a new awesome theme?</p>
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <div class="pull-left">
                                                        <img src="img/avatar3.png" class="img-circle" alt="user image" />
                                                    </div>
                                                    <h4>
                                                        Sales
                                                        <small><i class="fa fa-clock-o"></i> Yesterday</small>
                                                    </h4>
                                                    <p>Why not buy a new awesome theme?</p>
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <div class="pull-left">
                                                        <img src="img/avatar3.png" class="img-circle" alt="user image" />
                                                    </div>
                                                    <h4>
                                                        Reviewers
                                                        <small><i class="fa fa-clock-o"></i> 2 days</small>
                                                    </h4>
                                                    <p>Why not buy a new awesome theme?</p>
                                                </a>
                                            </li>
                                        </ul>
                                    </li>
                                    <li class="footer"><a target="_blank" href="#">See All Messages</a>
                                    </li>
                                </ul>
                            </li>
                            <li class="dropdown notifications-menu">
                                <a target="_blank" href="#" class="dropdown-toggle" data-toggle="dropdown">
                                    <i class="livicon" data-name="bell" data-loop="true" data-color="#ccc" data-hovercolor="#fff" data-size="28"></i>
                                    <span class="label label-warning">10</span>
                                </a>
                                <ul class="dropdown-menu">
                                    <li class="header">You have 10 notifications</li>
                                    <li>
                                        <!-- inner menu: contains the actual data -->
                                        <ul class="menu">
                                            <li>
                                                <a target="_blank" href="#">
                                                    <i class="ion ion-ios7-people info"></i> 5 members joined today
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <i class="fa fa-warning danger"></i> Very long description here...
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <i class="fa fa-users warning"></i> 5 new members joined
                                                </a>
                                            </li>

                                            <li>
                                                <a target="_blank" href="#">
                                                    <i class="ion ion-ios7-cart success"></i> 25 sales made
                                                </a>
                                            </li>
                                            <li>
                                                <a target="_blank" href="#">
                                                    <i class="ion ion-ios7-person danger"></i> You changed your
                                                </a>
                                            </li>
                                        </ul>
                                    </li>
                                    <li class="footer"><a target="_blank" href="#">View all</a>
                                    </li>
                                </ul>
                            </li>
                            <li class="dropdown user user-menu">
                                <a target="_blank" href="#" class="dropdown-toggle" data-toggle="dropdown" style="width:100px; padding:7px !important">
                                    <img src="img/avatar3.png" width="35" class="img-circle img-responsive pull-left" height="35" alt="riot">
                                    <div class="riot">Riot <i class="caret pull-right"></i>
                                    </div>
                                </a>
                                <ul class="dropdown-menu">
                                    <!-- User image -->
                                    <li class="user-header bg-light-blue">
                                        <img src="img/avatar3.png" class="img-circle" alt="User Image" />
                                        <p>Riot Zeast Captain</p>

                                    </li>
                                    <!-- Menu Body -->
                                    <li role="presentation" class="divider"></li>
                                    <li><a target="_blank" href="#"><i class="livicon" data-name="user" data-s="18"></i> My Profile</a>
                                    </li>
                                    <li role="presentation"></li>
                                    <li><a target="_blank" href="#"><i class="livicon" data-name="gears" data-s="18"></i> Account Settings</a>
                                    </li>
                                    <li role="presentation" class="divider"></li>
                                    <!-- Menu Footer-->
                                    <li class="user-footer">
                                        <div class="pull-left"><a target="_blank" href="#"><i class="livicon" data-name="lock" data-s="18"></i> Lock</a>
                                        </div>
                                        <div class="pull-right"><a target="_blank" href="#"><i class="livicon" data-name="sign-out" data-s="18"></i> Logout</a>
                                        </div>
                                    </li>
                                </ul>
                            </li>
                        </ul>
                    </div>
                </nav>
</header>
```

