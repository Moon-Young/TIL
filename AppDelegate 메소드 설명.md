# AppDelegate 의 역할 알아보기 :)

#### @UIApplication 어노테이션이 붙은 사용자 정의 클래스를 UIApplication의 delegate로 사용합니다.
<pre>
<code>
@UIApplicationMain 
class AppDelegate: UIResponder, UIApplicationDelegate, 
</code>
</pre>

#### UIWindow는 View를 담는 컨테이너 역할
<pre>
<code>
var window: UIWindow?
</code>
</pre>



#### 앱을 실행하면 호출되는 delegate 메소드. <br> launchOptions 파라미터로 앱이 실행되게 된 이유 (푸시를 통한 실행) 등이 포함되어 실행된다. <br> return은 왜 true로 고정되어 있을까?<br> false로 바꿔도 앱은 정상적으로 실행되며, 아무 문제 없다. <br> return 값은 앱이 URL ( App Scheme ) 으로 실행된 경우 유효하다. URL로 실행 된 경우 launchOptions에 URL이 넘어오며 return을 false로 하면 openURL로 url을 오픈하지 않고 넘어간다.

<pre>
<code>
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.
        return true
    }
</code>
</pre>

#### 앱이 화면에 뜬 이후 실행되는 메소드. <br> 사실 WillBecomeActive도 있지만 자주 사용하지 않아서인지 AppDelegate에 기본적으로 override된 메소드는 applicationDidBecomeActive 였다.
<br> 앱이 백그라운드로 간 이후, 다시 포어그라운드로 올라온 이후에도 실행되는 메소드입니다.
<pre>
<code>
func applicationDidBecomeActive(_ application: UIApplication) {
        // Restart any tasks that were paused (or not yet started) while the application was inactive. If the application was previously in the background, optionally refresh the user interface.
    }
</code>
</pre>

#### 홈 버튼을 누르면 앱은 백그라운드로 이동합니다. 가장 먼저 App이 포커스를 잃으면서 실행되는 메소드입니다.<br>
템플릿 설명에 다르면 태스크 일시정지, 타이머 비활성화, 게임의 경우 일시정지를 처리하는 로직을 구현해야 하는 메소드입니다.
<pre>
<code>
func applicationWillResignActive(_ application: UIApplication) {
  }
</code>
</pre>




#### 앱이 백그라운드로 이동하여 더이상 앱이 보이지 않은 이후 호출되는 메소드. <br>
이 메소드에서는 공유자원 해제, 유저 데이터 저장 등의 로직을 구현해야합니다.
<pre>
<code>
func applicationDidEnterBackground(_ application: UIApplication) {
  }
</code>
</pre>

#### 앱이 다시 포어그라운드로 올라올 때 호출되는 메소드로, 보통 API를 통해 앱의 상태를 갱신할 때 사용합니다. 버전체크, 메인테이닝 체크 등..
<pre>
<code>
func applicationWillEnterForeground(_ application: UIApplication) {
  }
</code>
</pre>
