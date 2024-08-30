<template>
  <header id="header">
    <div class="globalHeader">
      <nav id="globalNav">
        <div class="globalnav-content">
          <ul>
            <li>
              <button @click="goLink('/')">
                <svg height="44" viewBox="0 0 14 44" width="14" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="m13.0729 17.6825a3.61 3.61 0 0 0 -1.7248 3.0365 3.5132 3.5132 0 0 0 2.1379 3.2223 8.394 8.394 0 0 1 -1.0948 2.2618c-.6816.9812-1.3943 1.9623-2.4787 1.9623s-1.3633-.63-2.613-.63c-1.2187 0-1.6525.6507-2.644.6507s-1.6834-.9089-2.4787-2.0243a9.7842 9.7842 0 0 1 -1.6628-5.2776c0-3.0984 2.014-4.7405 3.9969-4.7405 1.0535 0 1.9314.6919 2.5924.6919.63 0 1.6112-.7333 2.8092-.7333a3.7579 3.7579 0 0 1 3.1604 1.5802zm-3.7284-2.8918a3.5615 3.5615 0 0 0 .8469-2.22 1.5353 1.5353 0 0 0 -.031-.32 3.5686 3.5686 0 0 0 -2.3445 1.2084 3.4629 3.4629 0 0 0 -.8779 2.1585 1.419 1.419 0 0 0 .031.2892 1.19 1.19 0 0 0 .2169.0207 3.0935 3.0935 0 0 0 2.1586-1.1368z">
                  </path>
                </svg>
              </button>
            </li>
            <li 
              v-for="(category, idx) in categorys" 
              :key="'category_' + idx"
              :class="{ 'dropdown': true, 'show-dropdown': idx === activeDropdown, 'min-none': true }"
              @click="goLink(category.to)" 
              @mouseenter="showDropdown(idx)" 
              @mouseleave="hideDropdown"
            >
              <button>{{ category.name }}</button>
              <transition name="fade">
                <div v-show="idx === activeDropdown" class="dropdown-menu">
                  <div class="dropdown-content">
                    <div 
                      v-for="(subtitle, subIdx) in category.subtitles" 
                      :key="'subtitle_' + subIdx" 
                      class="drpdn"
                    >
                      <div class="drpdn-sub">
                        <div class="drpdn-subtitle">{{ subtitle.title }}</div>
                        <ul>
                          <li 
                            v-for="(link, linkIdx) in subtitle.links" 
                            :key="'link_' + linkIdx"
                          >
                            {{ link }}
                          </li>
                        </ul>
                      </div>
                    </div>
                  </div>
                </div>
              </transition>
            </li>
            <div class="flex justify-end items-center gap-[16px]">
              <li 
                :class="{ 'dropdown': true, 'show-dropdown': searchDropdown }" 
                @mouseleave="hideDropdown"
              >
                <button @click="toggleSearchDropdown">
                  <svg xmlns="http://www.w3.org/2000/svg" width="15px" height="44px" viewBox="0 0 15 44">
                    <path
                      d="M14.298,27.202l-3.87-3.87c0.701-0.929,1.122-2.081,1.122-3.332c0-3.06-2.489-5.55-5.55-5.55c-3.06,0-5.55,2.49-5.55,5.55 c0,3.061,2.49,5.55,5.55,5.55c1.251,0,2.403-0.421,3.332-1.122l3.87,3.87c0.151,0.151,0.35,0.228,0.548,0.228 s0.396-0.076,0.548-0.228C14.601,27.995,14.601,27.505,14.298,27.202z M1.55,20c0-2.454,1.997-4.45,4.45-4.45 c2.454,0,4.45,1.997,4.45,4.45S8.454,24.45,6,24.45C3.546,24.45,1.55,22.454,1.55,20z">
                    </path>
                  </svg>
                </button>
                <transition name="fade">
                  <div v-if="searchDropdown" class="dropdown-menu">
                    <div class="dropdown-content">
                      <div class="drpdn-search">
                        <div class="search-input">
                          <div>
                            <svg width="38" height="40" viewBox="0 0 38 40" xmlns="http://www.w3.org/2000/svg">
                              <path
                                d="m28.6724 27.8633-5.07-5.07c-.0095-.0095-.0224-.0122-.032-.0213a7.9967 7.9967 0 1 0 -1.8711 1.7625c.0254.03.0357.0681.0642.0967l5.07 5.07a1.3 1.3 0 0 0 1.8389-1.8379zm-18.0035-10.0033a6.5447 6.5447 0 1 1 6.545 6.5449 6.5518 6.5518 0 0 1 -6.545-6.5449z">
                              </path>
                            </svg>
                          </div>
                          <div><input type="text" placeholder="apple.com 검색하기"></div>
                        </div>
                        <div class="search-link">
                          <div class="link">빠른 링크</div>
                          <button>
                            <span>
                              <svg height="16" viewBox="0 0 9 16" width="9" xmlns="http://www.w3.org/2000/svg">
                                <path
                                  d="m8.6124 8.1035-2.99 2.99a.5.5 0 0 1 -.7071-.7071l2.1366-2.1364h-6.316a.5.5 0 0 1 0-1h6.316l-2.1368-2.1367a.5.5 0 0 1 .7071-.7071l2.99 2.99a.5.5 0 0 1 .0002.7073z">
                                </path>
                              </svg>
                            </span>
                            <span>Apple Store Online에서 쇼핑하기</span>
                          </button>
                          <button>
                            <span>
                              <svg height="16" viewBox="0 0 9 16" width="9" xmlns="http://www.w3.org/2000/svg">
                                <path
                                  d="m8.6124 8.1035-2.99 2.99a.5.5 0 0 1 -.7071-.7071l2.1366-2.1364h-6.316a.5.5 0 0 1 0-1h6.316l-2.1368-2.1367a.5.5 0 0 1 .7071-.7071l2.99 2.99a.5.5 0 0 1 .0002.7073z">
                                </path>
                              </svg>
                            </span>
                            <span>액세서리</span>
                          </button>
                          <button>
                            <span>
                              <svg height="16" viewBox="0 0 9 16" width="9" xmlns="http://www.w3.org/2000/svg">
                                <path
                                  d="m8.6124 8.1035-2.99 2.99a.5.5 0 0 1 -.7071-.7071l2.1366-2.1364h-6.316a.5.5 0 0 1 0-1h6.316l-2.1368-2.1367a.5.5 0 0 1 .7071-.7071l2.99 2.99a.5.5 0 0 1 .0002.7073z">
                                </path>
                              </svg>
                            </span>
                            <span>AirPods</span>
                          </button>
                          <button>
                            <span>
                              <svg height="16" viewBox="0 0 9 16" width="9" xmlns="http://www.w3.org/2000/svg">
                                <path
                                  d="m8.6124 8.1035-2.99 2.99a.5.5 0 0 1 -.7071-.7071l2.1366-2.1364h-6.316a.5.5 0 0 1 0-1h6.316l-2.1368-2.1367a.5.5 0 0 1 .7071-.7071l2.99 2.99a.5.5 0 0 1 .0002.7073z">
                                </path>
                              </svg>
                            </span>
                            <span>AirTag</span>
                          </button>
                          <button>
                            <span>
                              <svg height="16" viewBox="0 0 9 16" width="9" xmlns="http://www.w3.org/2000/svg">
                                <path
                                  d="m8.6124 8.1035-2.99 2.99a.5.5 0 0 1 -.7071-.7071l2.1366-2.1364h-6.316a.5.5 0 0 1 0-1h6.316l-2.1368-2.1367a.5.5 0 0 1 .7071-.7071l2.99 2.99a.5.5 0 0 1 .0002.7073z">
                                </path>
                              </svg>
                            </span>
                            <span>Apple Trade in</span>
                          </button>
                        </div>
                      </div>
                    </div>
                  </div>
                </transition>
              </li>
              <li 
                :class="{ 'dropdown': true, 'show-dropdown': cartDropdown }" 
                @mouseleave="hideDropdown"
              >
                <button @click="toggleCartDropdown">
                  <svg height="44" viewBox="0 0 14 44" width="14" xmlns="http://www.w3.org/2000/svg">
                    <path
                      d="m11.3535 16.0283h-1.0205a3.4229 3.4229 0 0 0 -3.333-2.9648 3.4229 3.4229 0 0 0 -3.333 2.9648h-1.02a2.1184 2.1184 0 0 0 -2.117 2.1162v7.7155a2.1186 2.1186 0 0 0 2.1162 2.1167h8.707a2.1186 2.1186 0 0 0 2.1168-2.1167v-7.7155a2.1184 2.1184 0 0 0 -2.1165-2.1162zm-4.3535-1.8652a2.3169 2.3169 0 0 1 2.2222 1.8652h-4.4444a2.3169 2.3169 0 0 1 2.2222-1.8652zm5.37 11.6969a1.0182 1.0182 0 0 1 -1.0166 1.0171h-8.7069a1.0182 1.0182 0 0 1 -1.0165-1.0171v-7.7155a1.0178 1.0178 0 0 1 1.0166-1.0166h8.707a1.0178 1.0178 0 0 1 1.0164 1.0166z">
                    </path>
                  </svg>
                </button>
                <transition name="fade">
                  <div v-if="cartDropdown" class="dropdown-menu">
                    <div class="dropdown-content">
                      <div class="drpdn-cart">
                        <div class="cart-title">장바구니가 비어있습니다.</div>
                        <div class="cart-login">저장해둔 항목이 있는지 확인하려면 <a href="#">로그인</a>하세요.</div>
                        <div class="profile">
                          <div class="profile-title">내 프로필</div>
                          <button class="profile-list">
                            <div>
                              <svg 
                                id="Outlined" xmlns="http://www.w3.org/2000/svg" class="ac-gn-bagview-nav-svgicon"
                                width="16" height="25" viewBox="0 0 16 25">
                                <g id="shippingbox_compact">
                                  <rect id="box_" width="16" height="25" fill="none"></rect>
                                  <path 
                                    id="art_"
                                    d="M14.5146,9.5234a2.56,2.56,0,0,0-1.11-1.4228l-4.25-2.3975a2.3909,2.3909,0,0,0-2.31,0l-4.25,2.3975a2.2971,2.2971,0,0,0-.6025.5107A2.2684,2.2684,0,0,0,1.4,10.1475v4.705a2.3546,2.3546,0,0,0,1.1953,2.0469l4.25,2.3975a2.3541,2.3541,0,0,0,2.31,0l4.25-2.3975A2.3546,2.3546,0,0,0,14.6,14.8525v-4.705A2.3322,2.3322,0,0,0,14.5146,9.5234ZM7.4,12.9453v5.2871L3.1851,15.8545a1.153,1.153,0,0,1-.585-1.002L2.603,10.24Zm.6-1.04L3.147,9.17a.4347.4347,0,0,1,.0385-.0244l1.7623-.9941,4.895,2.7158Zm5.4-1.666v4.6132a1.153,1.153,0,0,1-.585,1.002L8.6,18.2324V12.9453ZM8.5649,6.748l4.25,2.3975a.4347.4347,0,0,1,.0385.0244l-1.7842,1.0059L6.1733,7.46l1.2618-.712A1.1731,1.1731,0,0,1,8.5649,6.748Z"
                                    fill="6E6E73"></path>
                                </g>
                              </svg>
                            </div>
                            <div>주문</div>
                          </button>
                          <button class="profile-list">
                            <div>
                              <svg 
                                id="Outlined" xmlns="http://www.w3.org/2000/svg" class="ac-gn-bagview-nav-svgicon"
                                width="16" height="25" viewBox="0 0 16 25">
                                <g id="bookmark_compact">
                                  <rect id="box_" width="16" height="25" fill="none"></rect>
                                  <path 
                                    id="art_"
                                    d="M10.3,5.15H5.7a2.3022,2.3022,0,0,0-2.3,2.3V19.0381a.8642.8642,0,0,0,.19.5869.67.67,0,0,0,.5313.2246.7441.7441,0,0,0,.438-.1465,4.8685,4.8685,0,0,0,.5366-.4765l2.8931-2.8858,2.9165,2.8867a6.4062,6.4062,0,0,0,.5307.4717.7286.7286,0,0,0,.4429.15.6684.6684,0,0,0,.5308-.2246.8619.8619,0,0,0,.19-.5869V7.45A2.3022,2.3022,0,0,0,10.3,5.15ZM4.6,7.45A1.102,1.102,0,0,1,5.7,6.35h4.6A1.102,1.102,0,0,1,11.4,7.45l-.0005,10.5781L8.832,15.4863a1.186,1.186,0,0,0-1.665.001L4.6,18.0293Z"
                                    fill="6E6E73"></path>
                                </g>
                              </svg>
                            </div>
                            <div>관심목록</div>
                          </button>
                          <button class="profile-list">
                            <div>
                              <svg 
                                id="Outlined" xmlns="http://www.w3.org/2000/svg" class="ac-gn-bagview-nav-svgicon"
                                width="16" height="25" viewBox="0 0 16 25">
                                <g id="gear_compact">
                                  <rect id="box_" width="16" height="25" fill="none"></rect>
                                  <path 
                                    id="art_"
                                    d="M15.6094,12.3252a.5142.5142,0,0,0-.2959-.2959l-.5972-.2324a6.6665,6.6665,0,0,0-.16-.917l.4809-.42a.5172.5172,0,0,0-.3291-.9073l-.6372-.0136c-.0654-.1377-.1343-.2784-.2139-.4151s-.1635-.2636-.2519-.3935l.3076-.5576a.517.517,0,0,0-.62-.7393l-.6035.2051a6.68,6.68,0,0,0-.7134-.5977l.0986-.6328a.5172.5172,0,0,0-.43-.5918.54.54,0,0,0-.4052.1084l-.5015.4033A6.911,6.911,0,0,0,9.87,6.01l-.124-.6328a.5178.5178,0,0,0-.9512-.167l-.333.5507a7.2576,7.2576,0,0,0-.92.0039L7.2056,5.207a.518.518,0,0,0-.9512.167l-.125.6377a6.6192,6.6192,0,0,0-.8652.31l-.501-.4063a.5176.5176,0,0,0-.8364.4834l.0991.6358a6.6073,6.6073,0,0,0-.7017.5947L2.71,7.417a.5173.5173,0,0,0-.6211.7392l.3134.5694a6.7192,6.7192,0,0,0-.4653.7959l-.6421.0117a.516.516,0,0,0-.5083.5264.52.52,0,0,0,.1763.38l.4849.4238a6.8261,6.8261,0,0,0-.16.9111l-.6006.23a.5176.5176,0,0,0-.001.9658l.5972.2324a6.6665,6.6665,0,0,0,.16.917l-.4809.419a.5184.5184,0,0,0-.05.7314.52.52,0,0,0,.3789.1758l.6367.0137c.063.1318.1333.2754.2144.416.0673.1172.143.2246.2163.3281l.04.0566-.312.5664a.5176.5176,0,0,0,.2036.7032.52.52,0,0,0,.416.0361l.5967-.2031a6.82,6.82,0,0,0,.7207.5937l-.0991.6348a.5153.5153,0,0,0,.0933.3857.5187.5187,0,0,0,.7421.0977l.5064-.4082a6.6137,6.6137,0,0,0,.8628.3193l.1245.6358a.5139.5139,0,0,0,.22.33.53.53,0,0,0,.3877.0782.5193.5193,0,0,0,.3433-.24l.3388-.56.0577.0049a4.8076,4.8076,0,0,0,.7871.0019l.0669-.0058.3383.5625a.518.518,0,0,0,.9512-.167l.1245-.6348a6.6152,6.6152,0,0,0,.8589-.3193l.5088.4131a.5176.5176,0,0,0,.8364-.4834l-.0991-.6358a6.6173,6.6173,0,0,0,.7017-.5947l.6142.2119a.5174.5174,0,0,0,.6211-.7392l-.3135-.5694a6.6548,6.6548,0,0,0,.4649-.7959l.6421-.0117a.5168.5168,0,0,0,.5088-.5264.5166.5166,0,0,0-.1768-.38l-.4849-.4238a6.6694,6.6694,0,0,0,.16-.9111l.6006-.2315a.5177.5177,0,0,0,.2969-.6689ZM6.4941,13.9043,4.7666,16.8926a5.4449,5.4449,0,0,1,.0044-8.792L6.5,11.0986A2.0525,2.0525,0,0,0,6.4941,13.9043Zm2.1646-1.7822a.7608.7608,0,1,1-.4609-.3555A.7543.7543,0,0,1,8.6587,12.1221ZM7.54,10.499,5.8154,7.5068A5.4579,5.4579,0,0,1,7.9907,7.041h.0239a5.4693,5.4693,0,0,1,5.4068,4.8633l-3.457-.0029a2.0363,2.0363,0,0,0-.18-.43A2.0586,2.0586,0,0,0,7.54,10.499Zm-.0058,4.0049a2.0556,2.0556,0,0,0,2.435-1.4023l3.4512.0029a5.4455,5.4455,0,0,1-7.6147,4.3877Z"
                                    fill="6E6E73"></path>
                                </g>
                              </svg>
                            </div>
                            <div>계정</div>
                          </button>
                          <button class="profile-list">
                            <div>
                              <svg 
                                id="Outlined" xmlns="http://www.w3.org/2000/svg" class="ac-gn-bagview-nav-svgicon"
                                width="16" height="25" viewBox="0 0 16 25">
                                <g id="person.crop.circle_compact">
                                  <rect id="box_" width="16" height="25" fill="none"></rect>
                                  <path 
                                    id="art_"
                                    d="M15.09,12.5a7.1,7.1,0,1,1-7.1-7.1A7.1077,7.1077,0,0,1,15.09,12.5ZM7.99,6.6a5.89,5.89,0,0,0-4.4609,9.7471c.6069-.9658,2.48-1.6787,4.4609-1.6787s3.8545.7129,4.4615,1.6787A5.89,5.89,0,0,0,7.99,6.6ZM7.99,8.4A2.5425,2.5425,0,0,0,5.5151,11,2.5425,2.5425,0,0,0,7.99,13.6,2.5424,2.5424,0,0,0,10.4653,11,2.5424,2.5424,0,0,0,7.99,8.4Z"
                                    fill="6E6E73"></path>
                                </g>
                              </svg>
                            </div>
                            <div>로그인</div>
                          </button>
                        </div>
                      </div>
                    </div>
                  </div>
                </transition>
              </li>
              <li :class="{ 'dropdown': true, 'min-menu': true, 'show-dropdown': minMenuDropdown }">
                <button @click="toggleminMenuDropdown">
                  <svg width="18" height="18" viewBox="0 0 18 18">
                    <polyline 
                      id="globalnav-menutrigger-bread-bottom" fill="none" stroke="currentColor"
                      stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"
                      :points="minMenuDropdown ? '3.5 15, 15 3.5' : '2 12, 16 12'"
                      class="globalnav-menutrigger-bread globalnav-menutrigger-bread-bottom">
                    </polyline>
                    <polyline 
                      id="globalnav-menutrigger-bread-top" fill="none" stroke="currentColor" stroke-width="1.2"
                      stroke-linecap="round" stroke-linejoin="round"
                      :points="minMenuDropdown ? '3.5 3.5, 15 15' : '2 5, 16 5'"
                      class="globalnav-menutrigger-bread globalnav-menutrigger-bread-top">
                    </polyline>
                  </svg>
                </button>
                <transition name="fade">
                  <div v-if="minMenuDropdown" class="dropdown-menu">
                    <div class="dropdown-content">
                      <div class="drpdn-minMenu">
                        <button
                          v-for="(category, idx) in categorys"
                          :key="'minmenu_' + idx"
                          @click="goLink(category.to)"
                        >
                          {{ category.name }}
                        </button>
                      </div>
                    </div>
                  </div>
                </transition>
              </li>
            </div>
          </ul>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data: () => ({
    categorys: [
      {
        name: '스토어',
        to: 'store',
        subtitles: [
          { title: '쇼핑하기', links:['최신 제품 쇼핑하기', 'Mac', 'iPad', 'iPhone', 'Apple Watch', '액세서리' ] },
          { title: '빠른 링크', links:['매장 찾기', '주문 상태', 'Apple Trade in', '할부 방식' ] },
          { title: '특별 할인 쇼핑하기', links:['인증 리퍼비쉬 제품', '교육', '비즈니스' ] }
        ]
      },
      {
        name: 'Mac',
        to: 'mac',
        subtitles: [
          { title: 'Mac 살펴보기', links:['Mac 모두 살펴보기', 'MacBook Air', 'MacBook Pro', 'iMac', 'Mac mini', 'Mac Studio', 'Mac Pro', '디스플레이'] },
          { title: 'Mac 쇼핑하기', links: ['Mac 쇼핑하기', 'Mac 액세서리', 'Apple Trade In', '할부 방식'] },
          { title: '그 외 Mac 관련 항목', links: ['Mac 지원', 'Mac을 위한 AppleCare+', 'macOS sonoma', 'Apple이 만든 앱', '연속성', 'iCloud+', 'Mac과 비즈니스', '교육'] }
        ]
      },
      {
        name: 'iPad',
        to: 'ipad',
        subtitles: [
          { title: 'iPad 살펴보기', links: ['iPad 모두 살펴보기', 'iPad Pro', 'iPad Air', 'iPad', 'iPad mini', 'Apple pencil', '키보드'] },
          { title: 'iPad 쇼핑하기', links: ['iPad 쇼핑하기', 'iPad 액세서리', 'Apple Trade In', '할부방식'] },
          { title: '그 외 iPad 관련 항목', links: ['iPad 지원', 'iPad를 위한 AppleCare+', 'iPadOS 17', 'Apple이 만든 앱', 'iCloud+', '교육'] }
        ]
      },
      {
        name: 'iPhone',
        to: 'iphone',
        subtitles: [
          { title: 'iPhone 살펴보기', links: ['iPhone 모두 살펴보기', 'iPhone 15 Pro', 'iPhone 15', 'iPhone 14', 'iPhone 13'] },
          { title: 'iPhone 쇼핑하기', links: ['iPhone 쇼핑하기', 'iPhone 액세서리', 'Apple Trade In', '할부 방식'] },
          { title: '그 외 iPhone 관련 항목', links: ['iPhone 지원', 'iPhone 위한 AppleCare+', 'iOS 17', 'Apple이 만든 앱', 'iPhone의 개인 정보 보호', 'iCloud+', 'Apple 지갑, Apple Pay', 'Siri'] }
        ]
      },
      {
        name: 'Watch',
        to: 'watch',
        subtitles: [
          { title: 'Watch 살펴보기', links: ['Apple Watch 모두 살펴보기', 'Apple Watch Series 9', 'Apple Watch Ultra 2', 'Apple Watch SE', 'Apple Watch Nike', 'Apple Watch Hermes'] },
          { title: 'iPhone 쇼핑하기', links: ['Apple Watch 쇼핑하기', 'Apple Watch Studio', 'Apple Watch 밴드', 'Apple Watch 액세서리', 'Apple Trade In', '할부방식'] },
          { title: '그 외 Watch 관련 항목', links: ['Apple Watch 지원', 'AppleCare+', 'WatchOS 10', 'Apple이 만든 앱'] }
        ]
      },
      {
        name: 'AirPods',
        to: 'airpods',
        subtitles: [
          { title: 'AirPods 살펴보기', links: ['AirPods 모두 살펴보기', 'AirPods Pro 2세대', 'AirPods 2세대', 'AirPods 3세대', 'AirPods Max'] },
          { title: 'AirPods 쇼핑하기', links: ['AirPods 쇼핑하기', 'AirPods 액세서리'] },
          { title: '그 외 AirPods 관련 항목', links: ['AirPods 지원', '헤드폰을 위한 AppleCare+', 'Apple Music'] }
        ]
      },
      {
        name: 'TV 및 홈',
        to: 'tvhome',
        subtitles: [
          { title: 'TV 및 홈 살펴보기', links: ['TV 및 홈 살펴보기', 'Apple TV 4K'] },
          { title: 'TV 및 홈 쇼핑하기', links: ['Apple TV 4K 쇼핑하기', 'Siri Remote 쇼핑하기', 'TV 및 홈 액세서리'] },
          { title: '그 외 TV 및 홈 관련 항목', links: ['Apple TV 지원', 'AppleCare+', 'Apple TV 앱', 'Apple TV+', '홈 앱', 'Apple Music', 'Siri', 'AirPlay'] }
        ]
      },
      {
        name: '엔터테인먼트',
        to: 'entertainment',
        subtitles: [
          { title: '엔터테인먼트 살펴보기', links: ['엔터테인먼트 살펴보기', 'Apple One', 'Apple TV+', 'Apple Music', 'Apple Arcade', 'Apple Podcasts', 'Apple Books', 'App Store'] },
          { title: '지원', links: ['Apple TV+ 지원', 'Apple Music 지원'] }
        ]
      },
      {
        name: '악세서리',
        to: 'acc',
        subtitles: [
          { title: '액세서리 쇼핑하기', links: ['액세서리 모두 쇼핑하기', 'Mac', 'iPad', 'iPhone', 'Apple Watch', 'AirPods', 'TV 및 홈'] },
          { title: '액세서리 살펴보기', links: ['Apple 제작 정품', 'Beats by Dr.Dre', 'AirTag'] }
        ]
      },
      {
        name: '고객지원',
        to: 'custom',
        subtitles: [
          { title: '지원 상황 살펴보기', links: ['iPhone', 'Mac', 'iPad', 'Watch', 'AirPods', 'Music', 'TV'] },
          { title: '도움 받기', links: ['커뮤니티', '보장 상태 확인하기', '수리', '문의하기'] },
          { title: '유용한 주제', links: ['AppleCare+ 구입하기', 'Apple ID 및 암호', '청구 및 구독', '나의 찾기', '손쉬운 사용'] }
        ]
      },
    ],
    activeDropdown: null,
    hideTimeout: null,
    searchDropdown: false,
    cartDropdown: false,
    minMenuDropdown: false,
  }),
  methods: {
    goLink(path) {
      this.$router.push(path)
    },
    showDropdown(index) {
      clearTimeout(this.hideTimeout);
      this.activeDropdown = index
      this.$emit('toggleDropdown', true)
    },
    hideDropdown() {
      this.hideTimeout = setTimeout(() => {
        this.activeDropdown = null
        this.searchDropdown = false
        this.cartDropdown = false
        this.$emit('toggleDropdown', false)
      }, 200)
    },
    toggleSearchDropdown() {
      this.searchDropdown = !this.searchDropdown;
      if (this.searchDropdown) {
        this.activeDropdown = null
        this.$emit('toggleDropdown', true) 
      } else {
        this.$emit('toggleDropdown', false) 
      }
    },
    toggleCartDropdown() {
      this.cartDropdown = !this.cartDropdown;
      if (this.cartDropdown) {
        this.activeDropdown = null
        this.$emit('toggleDropdown', true) 
      } else {
        this.$emit('toggleDropdown', false) 
      }
    },
    toggleminMenuDropdown() {
      this.minMenuDropdown = !this.minMenuDropdown;
      if (this.minMenuDropdown) {
        this.activeDropdown = null
        this.$emit('toggleDropdown', true) 
      } else {
        this.$emit('toggleDropdown', false) 
      }
    }
  }
}
</script>

<style scoped>
#header{
  @apply sticky top-0 w-full z-[9999];
}
.globalHeader{
  @apply bg-[#fafafc] relative;
}
.darkHeader .globalHeader {
  @apply bg-[#161617] relative;
}
.grayHeader .globalHeader {
  @apply bg-[#f5f5f7]
}
.globalnav-content{
  @apply m-[0_auto] w-full max-w-[1024px] p-[0px_16px];
}
.darkHeader .globalnav-content svg{
  @apply fill-[#d2d2d2];
}
.globalnav-content ul{
  @apply flex justify-between items-center;
}
.globalnav-content ul li{
  @apply flex items-center;
}
.globalnav-content ul li.min-menu{
  @apply hidden;
}
.globalnav-content ul li button{
  @apply p-[0px_8px] h-[44px] text-[#000] text-[13px] font-normal; 
}
.darkHeader .globalnav-content ul li button{
  @apply text-[#d2d2d2];
}
.dropdown-menu {
  @apply absolute left-0 top-[44px] w-full;
  max-height: 0;
  overflow: hidden;
  transition: all 0.3s ease-in-out;
}
.show-dropdown .dropdown-menu {
  @apply bg-[#fafafc] w-full;
  max-height: 500px;
}
.darkHeader .show-dropdown .dropdown-menu{
  @apply bg-[#161617];
}
.grayHeader .show-dropdown .dropdown-menu{
  @apply bg-[#f5f5f7];
}
.dropdown-content{
  @apply m-[0px_auto] w-full max-w-[1024px] p-[30px_20px] flex justify-start items-start gap-[40px];
}
.drpdn-subtitle{
  @apply text-[#7C7C81] text-[14px] font-normal;
}
.drpdn-sub ul{
  @apply flex flex-col items-start justify-start py-[12px];
}
.drpdn-sub ul li{
  @apply text-[#000] text-[24px] font-bold leading-[42px] cursor-pointer;
}
.dropdown-content .drpdn:first-child{
  @apply mr-[40px];
}
.dropdown-content .drpdn:nth-child(2) .drpdn-sub ul li, .dropdown-content .drpdn:nth-child(3) .drpdn-sub ul li{
  @apply text-[14px] leading-[30px];
}
.darkHeader .drpdn-sub ul li{
  @apply text-[#fafafc];
}
.fade-enter-active, .fade-leave-active {
  transition: all 0.3s ease-in-out, transform 0.3s ease-in-out;
}
.fade-enter, .fade-leave-to {
  transform: translateY(-10px);
}
.fade-leave-to .drpdn-subtitle, .fade-leave-to .drpdn-sub ul li, .fade-leave-to .drpdn-search, .fade-leave-to .drpdn-cart, .fade-leave-to .drpdn-minMenu{
  opacity: 0;
}
.drpdn-search, .drpdn-cart{
  @apply p-[30px_0px_80px];
}
.drpdn-search .search-input{
  @apply flex justify-start items-center gap-[5px] mb-[50px];
}
.drpdn-search .search-input input{
  @apply w-full border-none bg-inherit text-[30px] leading-[38px] text-[#7C7C81] font-bold placeholder:text-[#7c7c81];
}
.drpdn-search .search-link .link{
  @apply text-[#7c7c81] text-[14px] font-normal mb-[10px];
}
.drpdn-search .search-link button{
  @apply flex justify-start items-center gap-[10px] mb-[10px] !h-auto;
}
.drpdn-search .search-link button span{
  @apply text-[#000] font-bold text-[14px] leading-[24px];
}
.darkHeader .drpdn-search .search-link button span, .darkHeader .drpdn-cart .cart-title, .darkHeader .drpdn-cart .profile-list{
  @apply text-[#fafafc];
}
.drpdn-cart .cart-title{
  @apply text-[#000] font-bold text-[30px] leading-[38px] mb-[30px];
}
.drpdn-cart .cart-login{
  @apply text-[#7c7c81] text-[14px] font-normal mb-[30px];
}
.drpdn-cart .cart-login a{
  @apply underline text-[#2370B8];
}
.drpdn-cart .profile-title{
  @apply text-[#7c7c81] text-[14px] font-normal mb-[15px];
}
.drpdn-cart .profile-list{
  @apply flex justify-start items-center gap-[10px] mb-[15px] !h-auto text-[#000] !text-[14px] !font-bold;
}
.drpdn-minMenu{
  @apply w-full flex flex-col items-start justify-start;
}
.drpdn-minMenu button{
  @apply !text-[28px] !font-bold !text-[#1d1d1f] !h-[50px] !w-full text-left;
}
.darkHeader .drpdn-minMenu button{
  @apply !text-[#fafafc];
}
.min-menu .dropdown-menu{
  @apply !max-h-[100vh] !h-[100vh];
}
@media (max-width: 734px) {
  .min-none{
    @apply !hidden;
  }
  .globalnav-content ul li.min-menu{
    @apply !flex;
  }
}
</style>