<script>
import firebaseInstance from '../resources/firebase/index.js';
import { navigate } from "svelte-routing";

let email = firebaseInstance.getCurrentUserId().email
let userImage = "https://randomuser.me/api/portraits/men/10.jpg";
let anonAvatar = "https://randomuser.me/api/portraits/men/10.jpg";

console.log(JSON.stringify(firebaseInstance.getCurrentUserId()))

function onSignout() {
  firebaseInstance.signout();
  navigate("/", { replace: true });
}

</script>

<div class="header navbar">
<div class="header-container">
  <ul class="nav-left">
    <li>
      <a id="sidebar-toggle" class="sidebar-toggle">
        <i class="ti-menu" />
      </a>
    </li>
  </ul>
  <ul class="nav-right">
    <li class="dropdown">
    <a class="dropdown-toggle no-after peers fxw-nw ai-c lh-1" data-toggle="dropdown" aria-expanded="false">
        <div class="peer mR-10"><img class="w-2r bdrs-50p" src="https://randomuser.me/api/portraits/men/10.jpg" alt=""></div>
        <div class="peer"><span class="fsz-sm c-grey-900">{email}</span></div>
    </a>
    <ul class="dropdown-menu fsz-sm">
        <li><a href="#" class="d-b td-n pY-5 bgcH-grey-100 c-grey-700"><i class="ti-settings mR-10"></i> <span>Setting</span></a></li>
        <li><a href="#" class="d-b td-n pY-5 bgcH-grey-100 c-grey-700"><i class="ti-user mR-10"></i> <span>Profile</span></a></li>
        <li><a href="#" class="d-b td-n pY-5 bgcH-grey-100 c-grey-700"><i class="ti-email mR-10"></i> <span>Messages</span></a></li>
        <li role="separator" class="divider"></li>
        <li><a href="" class="d-b td-n pY-5 bgcH-grey-100 c-grey-700"><i class="ti-power-off mR-10"></i> <span>Logout</span></a></li>
    </ul>
  </li>
  </ul>
</div>
</div>
