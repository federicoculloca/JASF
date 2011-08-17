package org.jasf;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.os.PowerManager;
import android.view.WindowManager;

public class Jasf extends Activity {

	private WindowManager.LayoutParams lp;
	private PowerManager pm;
	PowerManager.WakeLock wl;

	/** Called when the activity is first created. */
	@Override
	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.main);
		lp = getWindow().getAttributes();
	}

	@Override
	public void onResume() {
		super.onResume();
		pm = (PowerManager) getSystemService(Context.POWER_SERVICE);
		wl = pm.newWakeLock(
				PowerManager.SCREEN_BRIGHT_WAKE_LOCK, "JASF");
		wl.acquire();
		lp.screenBrightness = 1;
		getWindow().setAttributes(lp);
	}

	@Override
	public void onStop() {
		super.onStop();
		wl.release();
	}
}