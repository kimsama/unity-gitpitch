## ScriptableObject

---

## Unity Audio
- Audio Source - 스피커
- Audio Listener - 귀

![Image-Absolute](images/sound01.jpg)

---

## Sound - Unity API

AudioSource.PlayOneShot


### Audio Manager

AudioManager.cs 

```csharp
using  System.Collections ;
using  System.Collections.Generic ;
using  UnityEngine ;

[CreateAssetMenu]
public  class  AudioManager : ScriptableObject
{
	public  void  PlayOneShot ( AudioClip  clip )
	{
		if (audioSource! = null ) {
			audioSource.PlayOneShot (clip);
		}
	}

	public AudioSource  audioSource { get ; set ;}
}
```

## Event Trigger

MonoBehaviourEventTrigger.cs

``` csharp
using  System.Collections ;
using  System.Collections.Generic ;
using  UnityEngine ;
using  UnityEngine.Events ;

public  class  MonoBehaviourEventTrigger : MonoBehaviour
{
	public UnityEvent  onAwake = new  UnityEvent ();
	public UnityEvent  onDestroy = new  UnityEvent ();

	void  Awake ()
	{
		onAwake.Invoke ();
	}

	void  OnDestroy ()
	{
		onDestroy.Invoke ();
	}
}
```
