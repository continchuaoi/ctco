<div id="player">
	<div class="item button" data-bind="
		click:previous,
		maskBtn:{css:'mainImage'}
		" id="previous"></div> 
	<div class="item button" data-bind="
		click:play,
		visible:!isPlay(),
		maskBtn:{hasOffset:false}
		" id="play" style="background-position: 0px 0%;"></div> 
	<div class="item button" data-bind="
		click:pause,
		visible:isPlay(),
		maskBtn:{css:'mainImage'}
		" id="pause" style="display: none; background-position: -32px 100%;"></div> 
	<div class="item button" data-bind="
		click:next,
		maskBtn:{css:'mainImage'}
		" id="next"></div> 
	<div class="text" id="title" data-bind="
		followLeft:'#seeker',
		">
    <a data-bind="text:display,attr:{
      href:current() ? current().url() : 'http://scmplayer.net'
      }" target="_blank" id="titleLink" href="https://www.youtube.com/watch?feature=player_embedded&amp;v=Sro4SN83OOE">gfg</a>
	</div> 
	<div class="item ui-slider ui-slider-horizontal ui-widget ui-widget-content ui-corner-all" data-bind="
		slider:playedFraction, 
		sliderOptions:{step:0.00001,min:0,max:1,pauseable:true}
		" id="seeker" style="left: 123px;"> 
		<div id="seekerSliderBase" class="ui-slider-handle ui-state-default ui-corner-all" style="left: 2.093%;"></div> 
		<div id="seekerBase"></div> 
		<div id="seekerBuffered" data-bind="
			style:{width:(loadedFraction()*100)+'%'}
			" style="width: 7.23863139410188%;"></div> 
	</div> 
	<div class="text" id="tooltip"> 
		<a href="http://scmplayer.net" id="scmLink" target="_blank"></a> 
	</div> 
	<div class="text item" id="timer" data-bind="text:timer">01:18|62:10</div> 
	<div class="item ui-slider-horizontal" data-bind="
		innerBound:{bound:'.bound',handle:'.ui-slider-handle'}
		" id="volume"> 
		<div class="bound ui-slider ui-slider-horizontal ui-widget ui-widget-content ui-corner-all" data-bind="
			slider:volume,
			sliderOptions:{liveUpdate:true},
			caption:'Volume: '+volume()+'%',
			captionOptions:{target:'#tooltip a',trigger:'slide'}
			" style="width: 56px; margin-left: 7px; margin-right: 7px;">
		<div class="ui-slider-handle ui-state-default ui-corner-all" id="volumeSlider" style="margin-left: -7px; left: 50%;"></div> 
		</div>
	</div> 
	<div class="item button" id="list" data-bind="maskBtn:{css:'mainImage',align:'right'},
		click:togglePlaylist,
		caption:'Toggle Playlist',
		captionOptions:{target:'#tooltip a',trigger:'hover'}
		"></div> 
	<div class="mainImage" id="baseRight"></div> 
	<div class="mainImage" id="baseLeft"></div> 
</div>
