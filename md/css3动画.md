CSS3新增选择器
	层级选择器
		~:
	结构性伪类选择器
		:nth-child
		:first-child
		:last-child

		:nth-of-type
		:first-of-type
		:last-of-type

	UI伪类选择器
		:checked
CSS3新增属性 
	border-radius
	box-sizing
	border-image
	font-face
	text-shadow
	box-shadow
	text-overflow
	background-image:url(),url();
	background-image:linear-gradient()
	background-size:
	background-orgin
	background-clip
	opacity
	resize


	transition	过渡
		transition-property:需要过渡的CSS属性    all
		transition-duration:需要过渡的时间		s  ms   5s   500ms
		transition-timing-function:动画效果;	ease linear ease-in ease-out ease-in-out
		transition-delay:		延迟时间

		注：
			1)常配合:hover :active :focus :checked 选择器一起使用
			2)具有中间值的CSS属性才可以过渡
	tranform	变形
		transform:变形
		2d----二维   x y
		transform-orgin:变形的中心点
			transform:	  translateX(200px);		       平移
					  translateY(200px);
					  translate(200px,300px);


					  rotateX(45deg)			旋转  正值表示顺时针 
					  rotateY()
					  rotate(36deg);


					  scaleX(0.5)				缩放
					  scaleY()
					  scale(x,y)


					  skewX(45deg)				倾斜	
					  skewY()
					  skew()



		transform-orgin:x y;
		transform-orgin:center center;
		transform-orgin:50% 50%;
			x:20px 20%  left/center/right
			y:20px 20%  top/center/bottom

	transform:rotate(360deg) scale(2) translate(200px,600px) skew(35deg);

	animation:	动画
	属性:
		animation-name				名称
		animation-duration			时间   s ms
		animation-timing-function	动画类型  ease linear ease-in 
		animation-delay				动画延迟时间 s ms
		animation-interation-count	动画播放次数 3  infinite（循环播放）
		animation-direction			动画播放方向	alternate  reverse  
		animation-fill-mode			动画播放模式    backwards forwards	both
		animation-play-state		动画时状态		running  paused

	animation:name 1s linear infinite alternate;

	规则1:
		@keyframes  name{
			from{
				css属性
			}
			to{
				css属性
			}
		}

	规则2:
		@keyframes  name{
			0%{
				css属性
			}
			10%{

			}
			20%{

			}
			25%{

			}
			100%{
				css属性
			}
		}


		tansform   3d变形











		动画

	.dh{
            width: 10px;
            height: 10px;
            border: 1px solid red;
            border-radius: 50%;
            background: red;
            animation: aa 1s ease 1s infinite;
        }

        @keyframes aa {
            from {
                background: red;
            }
            to {
                background: blue;
            }
        }
			









	

